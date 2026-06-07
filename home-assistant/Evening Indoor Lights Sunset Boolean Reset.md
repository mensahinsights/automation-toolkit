'''
alias: Evening Indoor Lights Sunset Boolean Reset
description: ""
triggers:
  - at: "23:59:59"
    trigger: time
actions:
  - target:
      entity_id: input_boolean.sunset_active_halifax
    action: input_boolean.turn_off

'''
