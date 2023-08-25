The deploy.yaml is combination of all the yaml files needed to deploy the famousquotes app

1) Search deploy.yaml for "image:"
2) use podman to pull and save the 2 images from internet (mariadb is 300+MB, famous-quotes is 800+MB. I cannot upload here)
3) copy and upload the images to the mirror registry
4) edit the deploy.yaml to change the image to point to mirror registry
5) login ocp
6) oc new-project famouschart (if the project is different name, you need to change all the namespace in deploy.yaml)
7) oc create -f deploy.yaml
8) oc expose svc famousapp-famouschart -n famouschart
9) oc get route famousapp-famouschart (copy url)
10) open browser and enter http://famousapp-famouschart-famouschart.apps.ocp4.example.com/random
11) take note the /random at the back of url
12) every refresh will display a random quote
13) to remove type: oc delete -f deploy.yaml
14) and: oc delete route famousapp-famouschart -n famouschart

