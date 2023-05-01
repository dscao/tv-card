
# TV Remote Card

**Sample overview:**

<img src="https://github.com/usernein/tv-card/blob/master/assets/screenshot.png" alt="screenshot" width="300"/>

Add this to your lovelace configuration if your tv is a Samsung Smart TV:

```yaml
type: custom:tv-card
entity: media_player.tv
title: Example 2
platform: samsungtv
power_row:
  - power
channel_row:
  - channel_up
  - info
  - channel_down
apps_row:
  - netflix
  - youtube
  - spotify
volume_row: slider
navigation_row: touchpad
source_row:
  - return
  - home
  - source
media_control_row:
  - rewind
  - play
  - pause
  - fast_forward
```

If you're not using Samsung, you may want to set custom buttons for your tv. [Check it out](https://github.com/usernein/tv-card/blob/master/README.md#notice).

Look at [README](https://github.com/usernein/tv-card/blob/master/README.md) for more information


my lovelace card:
```yaml
cards:
  - cards:
      - color: rgb(113, 113, 198)
        color_type: card
        icon: mdi:power
        name: 客厅电视机
        styles:
          card:
            - height: 80px
        tap_action:
          action: call-service
          service: esphome.tuya_ir_3530b5_transmit
          service_data:
            code: '48896:61965'
            repeat: 1
        type: custom:button-card
      - default: 'off'
        entity: switch.ketingtv
        states:
          'off':
            color: rgb(255, 0, 0)
            color_type: label-card
            name: 客厅电视盒子
            styles:
              card:
                - height: 80px
            type: custom:button-card
          'on':
            color: rgb(255, 255, 255)
            color_type: label-card
            name: 客厅电视盒子
            styles:
              card:
                - height: 80px
            type: custom:button-card
          playing:
            color: rgb(255, 255, 255)
            color_type: label-card
            name: 客厅电视盒子
            styles:
              card:
                - height: 80px
            type: custom:button-card
          paused:
            color: rgb(255, 255, 255)
            color_type: label-card
            name: 客厅电视盒子
            styles:
              card:
                - height: 80px
            type: custom:button-card
          idle:
            color: rgb(255, 255, 255)
            color_type: label-card
            name: 客厅电视盒子
            styles:
              card:
                - height: 80px
            type: custom:button-card
        type: custom:state-switch
      - color: rgb(119, 136, 153)
        color_type: card
        icon: mdi:power
        name: 机顶盒电源
        styles:
          card:
            - height: 80px
        tap_action:
          action: call-service
          service: esphome.tuya_ir_3530b5_transmit
          service_data:
            code: '56610:9180'
            repeat: 1
        type: custom:button-card
    type: horizontal-stack
  - type: custom:tv-card
    entity: media_player.ke_ting_dian_shi
    platform: tvbox_esphome_tuya_ir
    rows:
      apps_row:
        - power
        - tv_power
      source_row:
        - home
        - menu
        - return
      navigation_row: touchpad
      volume_row: buttons
    enable_double_click: true
    double_click_action: return
    custom_keys:
      tv_power:
        icon: mdi:television
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '48896:61965'
          repeat: 1
      up:
        icon: mdi:chevron-up
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:13770'
          repeat: 1
      down:
        icon: mdi:chevron-down
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:11730'
          repeat: 1
      left:
        icon: mdi:chevron-left
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:26265'
          repeat: 1
      right:
        icon: mdi:chevron-right
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:16065'
          repeat: 1
      enter:
        icon: mdi:checkbox-blank-circle
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:12750'
          repeat: 1
      return:
        icon: mdi:arrow-u-left-top
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:27285'
          repeat: 1
      menu:
        icon: mdi:menu
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:32130'
          repeat: 1
      power:
        icon: mdi:power
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:9180'
          repeat: 1
      home:
        icon: mdi:home
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:30600'
          repeat: 1
      volume_up:
        icon: mdi:volume-plus
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:32640'
          repeat: 1
      volume_down:
        icon: mdi:volume-minus
        service: esphome.tuya_ir_3530b5_transmit
        service_data:
          code: '56610:32385'
          repeat: 1
  - elements: []
    camera_image: camera.192_168_9_108
    type: picture-elements
  - cards:
      - color: rgb(255, 255, 255)
        color_type: card
        icon: mdi:volume-minus
        name: 电视机音量减
        styles:
          card:
            - height: 80px
        tap_action:
          action: call-service
          service: esphome.tuya_ir_3530b5_transmit
          service_data:
            code: '48896:48195'
            repeat: 1
        type: custom:button-card
      - color: rgb(255, 255, 255)
        color_type: card
        icon: mdi:volume-plus
        name: 电视机音量增
        styles:
          card:
            - height: 80px
        tap_action:
          action: call-service
          service: esphome.tuya_ir_3530b5_transmit
          service_data:
            code: '48896:47940'
            repeat: 1
        type: custom:button-card
    type: horizontal-stack
type: vertical-stack


```
