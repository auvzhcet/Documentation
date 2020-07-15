# CONTRIBUTING GUIDLINES

When contributing to this project, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.

Please note we have a code of conduct, please follow it in all your interactions with the project.

## PULL REQUEST PROCESS

1.Ensure any install or build dependencies are removed before the end of the layer when doing a build.

2.Update the `README.md` file with details of changes to the interface, this includes new environment variables, exposed ports, useful file locations and container parameters.

## Guidelines for adding images:

- All the images/figures/diagrams must always be added to a subfolder static. Make the folder if it isn't present
- ScreenShots should be considered over camera photos.
- The format of naming the images must be: <document_name>_. eg. online_CF_1.png for image in Online Crowd Funding.
- Images must be properly cropped, must not be showing OS or phone model/brand in the images.
- Every image must have caption about describing shortly about the figure. (Adding the source of the image would be better)

## PULL REQUEST GUIDELINES

1.Use the present tense imperative mood in the example commit message.

2.Conventional Commits may not need to specify present tense, imperative mood for verbs. Follow the use of use the common present tense, imperative mood practice.

3.You may merge the Pull Request in once you have the sign-off of two other developers, or if you do not have permission to do that, you may request the second reviewer to merge it for you.

### References

- [Convetional commits](https://www.conventionalcommits.org/en/v1.0.0/)

- [Scemantic PR](https://github.com/probot/semantic-pull-requests)

## Run docs with mkdocs locally

There are just few steps that you need to follow to run docs locally:

- Clone the repo

```console
$foo@bar git clone https://github.com/auvzhcet/Documentation
```

- Create a python virtual environment and activate it

```console
$foo@bar python3 -m venv venv
$foo@bar source venv/bin/activate
```

- Install the dependencies

```console
$foo@bar pip install -r requirements.txt
```

- Mkdocs serve

```console
foo@bar mkdocs serve
```
