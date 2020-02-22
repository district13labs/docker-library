# docker-images
Source for Docker configurations, images and Dockerfiles for District13 Softworks products and projects.

## Naming Standard
Images are built through an automated process on docker hub based off of the branch name.
Consider this pattern:
```
/(^DL-[0-9]+-{directory}-)([0-9.]+)/

Example: DL-4-golang-1.13
```
The first group of the regex comply with the general naming standard: `DL-4-golang-`.  
Where `DL` is the project abbreviation (docker-library), `4` is the issue number, `golang` is the subfolder.  
The subfolder also corresponds to the image name.

The second group of the regex - `1.13` - will produce the image tag. From a folder structure perspective the `Dockerfile` should be placed in this directory.  
In summary take this example:
```
Source:        /golang/1.13/Dockerfile
Branch:        DL-4-golang-1.13
Image:         district13labs/golang:1.13
```

Name the branches according to the standard. This will ensure that the images are built automatically.
