'''
alias: Evening Lights On Sequence
description: ""
triggers:
  - entity_id: input_boolean.sunset_active_halifax
    to: "on"
    trigger: state
actions:
  - action: light.turn_on
    metadata: {}
    target:
      entity_id: light.kitchen_stove_light
    data: {}
  - action: switch.turn_on
    metadata: {}
    target:
      entity_id:
        - switch.kitchen_under_cabinet_light
        - switch.hutch_light
    data: {}
  - delay: "00:03:00"
  - action: switch.turn_on
    metadata: {}
    target:
      entity_id: switch.master_bedroom_lamp
    data: {}
  - delay: "00:03:00"
  - action: light.turn_on
    metadata: {}
    target:
      entity_id: light.living_room_lamps
    data: {}
  - action: switch.turn_on
    metadata: {}
    target:
      entity_id: switch.sitting_room_lamp
    data: {}
  - delay: "00:04:00"
  - action: switch.turn_on
    metadata: {}
    target:
      entity_id: switch.basement_front_room_light
    data: {}

'''
