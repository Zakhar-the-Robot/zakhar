# zakhar

## About this repo

Zakhar is a robotics UX project. The main aim is to decrease the anxiety of users interacting with a robot.

**Assumed**: that the humans can interact the most effective and seamless with other living creatures

**Suggested**: to develop a robot's program structure in the way when basics of its logic are understandable from the robot's behavior. The behavior should mimic the animal one (as the human is an animal too).

Suggested to split the program into three parts:

- Conscious
- Unconscious
- Reflexes

**Conscious** represents simple intentions: move forward, sleep, run away, search something, etc.

**Unconscious** is responsible to solve how to realize those intentions: what to do for moving, how to behave if looking something etc.

**Reflexes** are small algorithms that can monopolize Unconscious from Conscious in some very explicit situations. E.g panic and fear if something breaking, convulsions if robot stuck and can't move as the conscious tells.

## Gears

The hugest parts of the project called gears. Currently there are 4 gears:
- zakhar_sensors
- zakhar-face-module
- zakhar_core
- zakhar_platform

## Related repos

Parts:

- [an-dr/zakhar_core: Software core for the Zakhar project](https://github.com/an-dr/zakhar_core)
- [an-dr/zakhar-face-module: Zakhar's part which is responsible for facial expressions](https://github.com/an-dr/zakhar-face-module)
- [an-dr/zakhar_faces: Zakhar's facial expressions](https://github.com/an-dr/zakhar_faces)
- [an-dr/zakhar_proto: Repository for expreriments and prototyping. Part of the Zakhar project](https://github.com/an-dr/zakhar_proto)
- [an-dr/zakhar_platform: Controlled from i2c and uart moving platform for zakhar](https://github.com/an-dr/zakhar_platform)

Demos:

- [an-dr/zakhar_demo1_reptile: The demo shows how unconditioned reflex on fast moving shadows affects to robot's behavior](https://github.com/an-dr/zakhar_demo1_reptile)

Experiments:

- [an-dr/r_giskard: Small project for experiments with unconditioned and conditioned reflexes](https://github.com/an-dr/r_giskard)

## Related articles

- [2019/06/01 - Zakhar’s Concept – technical_](https://blog.agramakov.me/2019/06/01/zakhars-concept/)
- [2019/05/05 - Zakhar relaunch: Zakha_ros – technical_](https://blog.agramakov.me/2019/05/05/zakhar-relaunch-zakha_ros/)
- [2019/01/10 - Zakhar the Robot – technical_](https://blog.agramakov.me/2019/01/10/zakhar-the-robot/)

## Milestones

1. [Reptile demo](https://github.com/an-dr/zakhar/releases/tag/reptile_demo)
    - Afraid of birds
    - Panics when afraid
2. Zakharos - moving the core to the [ROS](https://www.ros.org/)
3. Facial Emotions demo
    - Expresses fear if panics
    - Claustrophobia - sad if closed barrier
4. The heat of passion demo
    - If got hitten weak - angry
    - If got hitten strong - panics

### Future plans

- Zakha_rosV
    - Visual recognition
- ZakhaR.Giskard
    - Conditional and unconditional reflexes

## License

This work is licensed under the terms of the GPLv3 license.

For a copy, see: [LICENSE](LICENSE)

- site:    https://agramakov.me
- e-mail:  mail@agramakov.me

## Support

If you will decide to sopport me, you can send some pretty words on my email or just use the link

[Buy me a cup of tea](https://paypal.me/4ndr/1eur)

Any ammount will motivate me to develop the project. Thanks in advance!

## Todo

[Trello card](https://trello.com/c/bzF5YFop/3-zakhar)
