# BTA! Example Modpack 

Combines [packwiz](https://packwiz.infra.link/) and [unsup](https://git.sleeping.town/exa/unsup) to provide a single self-updating instance which can be managed from a git repository.

## How to modpack

- Follow the installation tutorial for packwiz: https://packwiz.infra.link/installation/
- Click "use this template".

<img width="290" height="200" alt="image" src="https://github.com/user-attachments/assets/a73aa6c7-1082-4bae-905f-8fa7b2ddab17" />

- Give it a creative name. It will need to be public for unsup to work, but private is fine for now.

<img width="779" height="693" alt="image" src="https://github.com/user-attachments/assets/dd4117ed-ec28-4dd2-beeb-ce522b2612bb" />

- Clone the repository. I use github desktop but any method should work fine.
- It does not have to be a github repository. Local git repos are fine too, as long as its publically accessible.

## Creating the instance

- Download and extract the instance in [releases](https://github.com/camoweed/Modpack-example-for-BTA/releases).
- Change the instance icon and instance.cfg to match your use case.

unsup uses a launch argument to function, so make sure that remains intact.

- In the /instance/minecraft/ folder edit "source" in ``unsup.ini`` to point at your pack.toml

<img width="818" height="155" alt="image" src="https://github.com/user-attachments/assets/287e5c33-33b8-4717-a025-750ccd066358" />

- To find the correct link, click ``pack.toml`` in github, then click ``raw``.

<img width="1829" height="548" alt="image" src="https://github.com/user-attachments/assets/09a8147d-0ba8-444f-945b-c35462618e14" />

- You can create your own "branding" icon at this website: https://qoi.y2k.diy/ (check convert to Base64)
- In order for the instance to see the pack.toml it must be publicly accessible.
- Once you have set the source, branding, and instance configuration you can add the contents of the /instance/ folder to a zip.

## Managing the pack

- See full reference for packwiz: https://packwiz.infra.link/reference/commands/packwiz/
- Open the /pack/ folder in a terminal and use

``packwiz url add "Name" <URL>``

then

``packwiz refresh``

<img width="967" height="131" alt="image" src="https://github.com/user-attachments/assets/71b6d9a9-d548-41e1-8138-9195aab93a1a" />

- You can use this to add a mod, texturepack, really any file thats on the internet.
- You can make a file optional using the [options] field.

Simply edit the ``mod.pw.toml`` file add and the following field:
```
[option]
optional = true
default = false
description = "Describe the mod!"
```
- Now that you have made changes locally and refreshed packwiz, you can add and commit your changes.
