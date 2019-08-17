DeepRacer with ChainerRL
---

This repository for running DeepRacer with ChainerRL locally.

Please follow the following step until `41.`.

https://gist.github.com/joezen777/6657bbe2bd4add5d1cdbd44db9761edb

After `42.`, please run the following instructions.

42. cd ../simulation_ws && docker build  -f Robomaker.docker -t deepracer_robomaker:chainerrl .
43. ..
44. edit the robomaker.env file to also reference your local ip address and your aws key and secret
45. docker run --rm --name dr --env-file ../robomaker.env --network sagemaker-local -p 8080:5900 -v $(pwd)/aws-robomaker-sample-application-deepracer/simulation_ws/src:/app/robomaker-deepracer/simulation_ws/src  -it deepracer_robomaker:chainerrl "./run.sh build distributed_training.launch"
46. Command Space, open vnc viewer, connect to 127.0.0.1:8080 to view Gazebo


