**English** | [简体中文](README.zh-CN.md)

# Anime Avatar Personalization

A reusable agent skill for character customization: **reference images / optional text → template head shape and UV fitting → hair and body generation → hair rigging and physics → complete head-and-neck assembly → motion tests and Unity output**.

**Prerequisite: provide the agent with a working anime-style VRChat avatar, preferably one whose head is already close to the target.** Also provide the target character references and the appearance and animation requirements for the task. Editable model assets and the relevant controllers are required. This skill includes no commercial avatar, generative model or account credentials, and does not require a particular avatar brand.

## Method overview

![Method overview: character references and an existing avatar head, hair and body generation, complete head-and-neck assembly, and motion testing](skills/anime-avatar-personalization/assets/method-overview.png)

**In our tests, the “3D Diffusion model” blocks in the diagram used Tripo.** The diagram illustrates the workflow; other implementations may use a different generation service. Hair bones, skin weights, physics and final assembly still require separate fitting and validation.

The depicted template and character are illustrative. Substitute the avatar and target character supplied by the user. Preserve the template's eyeballs, eyelids, oral structures and facial controls while customizing face shape, features and textures. Generate hair and a clothed body separately, assemble them with the complete head and neck, then run motion tests and verify the saved result after reopening it.

## Usage

The skill is in [`skills/anime-avatar-personalization`](skills/anime-avatar-personalization/SKILL.md). Its entry point is `SKILL.md`, with task-specific guides for the face, hair, body assembly and validation, plus a character worksheet. The directory can be installed independently; it does not depend on historical projects or experiment reports. The detailed skill instructions are currently in Simplified Chinese.

Give an agent that supports GitHub skill installation this repository URL and the path `skills/anime-avatar-personalization`, or copy the complete directory into your local Codex skills directory. Refresh skill discovery as required by your client, then invoke the skill.

```text
Install the anime-avatar-personalization skill from:
https://github.com/wuxiaoxi75-dot/anime-avatar-personalization/tree/main/skills/anime-avatar-personalization
```

```text
Use $anime-avatar-personalization.
I am providing an editable, working anime-style VRChat avatar and target character images.
Preserve the head and neck's facial animation capabilities while customizing the face,
hair and body. Show a combined preview of walking, crouching, gaze, blinking and speech
mouth shapes, and report any unfinished items.
```

Tools depend on the task: ImageGen or user-provided target images, a 3D generation service (Tripo in our tests), Blender, Unity, and compatible VRChat SDK and shader versions. Access to these tools and assets must be prepared separately; their installers, model weights and subscriptions are not included.

## What it provides

- Protection of the template head and neck's animation capabilities; face shape and UV fitting; separate treatment of eyes, brows and lashes.
- ImageGen eyelash artwork, eye-opening registration, multiple normal/smiling closure shapes, and a local outer-corner tail strategy.
- Hair generation and four-view selection, semantic hair groups, bone chains, proxy weights, and actual physics-off/on comparisons.
- Body generation interfaces, collar protection, complete head-and-neck transfer, and skeleton and rest-pose checks.
- Native continuous animation, save/reopen verification, defect classification and platform acceptance workflows.

This is a **method skill that guides an agent through implementation and validation**. It does not include a universal 3D generator or automatic rigger, and does not guarantee one-click success for arbitrary inputs. Generated garments, hair collisions, eyelid contact and automatic SDK inputs require per-character testing; unfinished or failed items must be reported.

## Repository scope

This repository contains only the general skill, character worksheet, UI metadata and a user-approved workflow illustration. It contains no historical experiment reports, logs, models, output videos, private projects, machine configuration or credentials.

The illustration depicts character and avatar appearances to explain the workflow. This repository does not grant rights to those characters, avatars, models or materials. Use assets you are authorized to use in actual projects.
