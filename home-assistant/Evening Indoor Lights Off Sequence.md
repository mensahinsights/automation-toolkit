
'''
alias: Evening Indoor Lights Off Sequence
description: ""
triggers:
  - trigger: time
    at: "23:05:00"
actions:
  - action: light.turn_off
    metadata: {}
    target:
      entity_id: light.kitchen_stove_light
    data: {}
  - action: switch.turn_off
    metadata: {}
    target:
      entity_id:
        - switch.kitchen_under_cabinet_light
        - switch.hutch_light
    data: {}
  - delay: "00:03:00"
  - action: switch.turn_off
    metadata: {}
    target:
      entity_id: switch.basement_front_room_light
    data: {}
  - delay: "00:03:00"
  - action: switch.turn_off
    metadata: {}
    target:
      entity_id: switch.sitting_room_lamp
    data: {}
  - action: light.turn_off
    metadata: {}
    target:
      entity_id: light.living_room_lamps
    data: {}
  - delay: "00:04:00"
  - action: switch.turn_off
    metadata: {}
    target:
      entity_id: switch.master_bedroom_lamp
    data: {}

'''
