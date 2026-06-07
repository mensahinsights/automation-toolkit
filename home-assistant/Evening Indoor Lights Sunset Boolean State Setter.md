'''
alias: Evening Indoor Lights Sunset Boolean State Setter
triggers:
  - minutes: /5
    trigger: time_pattern
conditions:
  - condition: time
    after: "16:00:00"
    before: "23:55:00"
actions:
  - choose:
      - conditions:
          - condition: template
            value_template: >
              {% set elev = state_attr('sun.sun', 'elevation') %} {% set m =
              now().month %} {% set wx = states('weather.halifax_forecast') %}
              {% set overcast = wx in [
                'cloudy',
                'fog',
                'hail',
                'lightning',
                'lightning-rainy',
                'partlycloudy',
                'pouring',
                'rainy',
                'snowy',
                'snowy-rainy',
                'exceptional'
              ] %} {% if overcast %}
                {{ elev < 10 }}
              {% elif m in [11, 12, 1, 2] %}
                {{ elev < 3 }}
              {% elif m in [5, 6, 7, 8] %}
                {{ elev < 3 }}
              {% else %}
                {{ elev < 4 }}
              {% endif %}
        sequence:
          - target:
              entity_id: input_boolean.sunset_active_halifax
            action: input_boolean.turn_on
    default:
      - target:
          entity_id: input_boolean.sunset_active_halifax
        action: input_boolean.turn_off

'''
