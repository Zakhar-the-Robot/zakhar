# Future plans

Detailed plans of the project development:

1. ✅ [Reptile Demo](https://github.com/an-dr/zakhar/releases/tag/reptile_demo) - implementing of a simple reptile instinct
    - Article: [Robot with the Conscious: Imitating animal behavior for reducing user’s anxiety](https://blog.agramakov.me/2020/05/29/robot-with-the-conscious/)
2. ✅ [Zakharos](https://github.com/an-dr/zakhar/releases/tag/zakharos) - moving the core to the [ROS](https://www.ros.org/)
3. 🟧 Emotions Demo - emotions and reflexes
    - New Features:
        - [wip] Implementing Emotions - behavior modificators, the more Conditioned response taught, the worse mood in response to the darkness
        - Claustrophobia - freeze and shiver if closed barrier and dark (instinct, unconditioned response)
        - Conditioned response - growing amount of claustrophobia situations leads to afraid the darkness, connecting darkness with claustrophobia
    - ✅ HW update:
        - Add a distance sensor to The Sensor platform.
        - Update Sensor MCU to ESP32
4. ⬜ ZakhaR.Giskard (Note: R.Giskard is a robot from novels by I.Asimov which could control human's emotions) - Further development of using conditioned and unconditioned responses
    - New Features:
        - If got hit weak - angry
        - If got hit strong - panics
        - Using the camera for detecting dark spots to hide
    - HW update:
        - Replace I2C with CANbus
5. ⬜ Animal Demo - showing the robot to users and collecting responses for making conclusions of this iteration
    - New Features:
        - Add any useful for user function
        - Visual recognition