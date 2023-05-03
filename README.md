# Level Generator

## Objective

Generate tile-based [levels](definitions/level_definition.md#what-is-a-level) in a [Metroidvania](https://en.wikipedia.org/wiki/Metroidvania) style.

The project is also a testbed for me to learn the [RUST programming language](https://www.rust-lang.org/).

## Roadmap

In order to have the project complete, some steps must be followed:

- Write the `Requirements` [✓](#requirements)
- Design the `Architecture` [✓](#architecture)
- Write the `User Stories` [(In Progress)](#user-stories)
- Implement the `User Stories`

While steps may be finished, they are subject to further reviews as the project matures.

## Requirements

All the requirements for the implementation are located in [their own section](requirements/README.md).

They should be clear enough as to explain the necessity and use of the project's capabilities.

## Architecture

Architectural drawings are essential to the understanding of the [requirements](#requirements), being laid out in [their own section](architecture/README.md).

This must allow readers to understand how the `requirements` interact with each other and give a more technical overview of the parts of the system.

## User Stories

Once the [requirements](#requirements) and [architecture](#architecture) are known and understood, one can break them down into the [User Stories](https://en.wikipedia.org/wiki/User_story).

The current list of `user Stories` is laid [here](user_stories/README.md).

## How to Use

This project should be used as a [git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

This way, the documentation is part of the implementation and can be tracked to specific commits.

This allows for easier maintenance as well as validation of the overall implementation.

When used as a `submodule`, the only section that may be ommited is the [Miscellaneous](#miscellaneous).

## Contribution

Contributions are welcome.

Send a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) and it will be reviewed for merge.

## Miscellaneous

### Reasoning

I am not a `game developer`. I am a `backend developer`, focused on "_enterprise software_".

As most developers, I started developing "_enterprise software_" to eventually become a `game developer` but now all my skills are oriented to this much different scenario.

Even so, I want to challenge myself: I want to try and make something that uses my skills to generate a game-kind-of-thing and maybe light the kindle I need to finally start game developing.

Here is hope.

### Credits

I have to thank [ThatGuyGlen](https://www.youtube.com/@ThatGuyGlen/) for their [breakdown on how Dead Cells was made](https://youtu.be/0MY03yNkuFI).
When they talked about level generation, I suddenly got the idea that _hey, I can do that!_

Suffice to say, I couldn't take that idea out of my head until I did something about it and now here we are.
