# Architecture and Code Structure

In this section, we will provide an overview of the architectural design and code structure of the R-TYPE game project. Understanding the high-level architecture and organization of the codebase is essential for anyone looking to contribute to or work on the project.

## Architectural Overview

The R-TYPE game follows a typical game architecture, consisting of several key components and systems that work together to create the gameplay experience. Here's an overview of the game's architecture:

### Game Engine
- The core of the game, responsible for managing game loops, rendering, and input handling.
- Provides the foundation for game mechanics and systems.

### Physics Engine
- Manages the physics simulation for player movement, enemy behavior, and interactions.
- Integrates collision detection and response.

### Graphics Engine
- Handles rendering of game assets, including characters, enemies, and background elements.
- Supports sprite animation and special effects.

### Game Logic
- Contains the high-level game rules and logic.
- Coordinates interactions between players, enemies, and game objects.

### Networking
- Enables multiplayer functionality by handling network communication.
- Synchronizes game state between clients and the server.

### User Interface (UI)
- Manages the in-game user interface, including menus, HUD elements, and player status.
- Provides a seamless and intuitive user experience.

## Code Structure and Organization

Our C++ codebase is organized following best practices to maintain clarity, modularity, and extensibility. Here's an overview of the code structure:

### Directory Structure

<details>
<summary>Root Directory</summary>


.
    ├── Assets/
    │   ├── acceleration1.gif
    │   ├── acceleration2.gif
    │   ├── boule1.gif
    │   ├── boule2.gif
    │   ├── explosion1.gif
    │   ├── explosion2.gif
    │   ├── test.cpp
    │   ├── tir10.gif
    │   ├── tir11.gif
    │   ├── tir12.gif
    │   ├── tir1.gif
    │   ├── tir2.gif
    │   ├── tir3.gif
    │   ├── tir4.gif
    │   ├── tir5.gif
    │   ├── tir6.gif
    │   ├── tir7.gif
    │   ├── tir8.gif
    │   ├── tir9.gif
    │   ├── vaisseau_droite.gif
    │   └── vaisseau_gauche.gif
    ├── Builder/
    │   └── builder.sh
    ├── CMake/
    │   └── CMakeLists.txt
    ├── Conan/
    │   └── conanfile.txt
    ├── Docker/
    │   └── Dockerfile
    ├── ECS/
    │   ├── AComponent.hpp
    │   ├── CMakeLists.txt
    │   ├── Components/
    │   │   ├── Acceleration.hpp
    │   │   ├── AllComponents.hpp
    │   │   ├── Collidable.hpp
    │   │   ├── Controllable.hpp
    │   │   ├── Drawable.cpp
    │   │   ├── Drawable.hpp
    │   │   └── Position.hpp
    │   ├── Entity.cpp
    │   ├── Entity.hpp
    │   ├── EntityManager.cpp
    │   ├── EntityManager.hpp
    │   ├── IComponent.hpp
    │   ├── main.cpp
    │   ├── Systems/
    │   │   ├── ASystem.hpp
    │   │   ├── ISystem.hpp
    │   │   ├── MovementSystem.cpp
    │   │   ├── MovementSystem.hpp
    │   │   ├── RenderSystem.cpp
    │   │   └── RenderSystem.hpp
    │   └── test.cpp
    ├── GUI/
    │   ├── Audio/
    │   │   ├── Audio.cpp
    │   │   └── Audio.hpp
    │   ├── CMakeLists.txt
    │   ├── Core/
    │   │   ├── Core.cpp
    │   │   └── Core.hpp
    │   ├── Entities/
    │   │   ├── Arms/
    │   │   │   ├── Missile.cpp
    │   │   │   └── Missile.hpp
    │   │   ├── Background/
    │   │   │   ├── shooting_star.cpp
    │   │   │   ├── shooting_star.hpp
    │   │   │   ├── star.cpp
    │   │   │   └── star.hpp
    │   │   ├── Player/
    │   │   │   ├── Player.cpp
    │   │   │   └── Player.hpp
    │   │   └── Power/
    │   │       ├── Powerup.cpp
    │   │       └── Powerup.hpp
    │   ├── Exceptions/
    │   │   └── Exception.hpp
    │   ├── Interface/
    │   │   ├── ICommunication.hpp
    │   │   └── IRenderer.hpp
    │   ├── main.cpp
    │   ├── Menu/
    │   │   ├── Menu.cpp
    │   │   └── Menu.hpp
    │   ├── Network/
    │   │   ├── NetworkCli.cpp
    │   │   └── NetworkCli.hpp
    │   └── Renderer/
    │       ├── Renderer.cpp
    │       └── Renderer.hpp
    ├── Images/
    │   └── hh.png
    ├── README.md
    ├── R-TYPE_DEV_DOCUMENTATION/
    │   ├── docs/
    │   │   ├── about.md
    │   │   ├── contact.md
    │   │   ├── FAQ.md
    │   │   ├── index.md
    │   │   ├── installation.md
    │   │   └── license.md
    │   ├── mkdocs.yml
    │   └── site/
    ├── R-TYPE.drawio - draw.io - Google Chrome 03_10_2023 11_11_15.png:Zone.Identifier
    ├── Server/
    │   ├── CMakeLists.txt
    │   ├── include/
    │   │   ├── binary_handling.hpp
    │   │   ├── Client_Handling.hpp
    │   │   ├── IMessage.hpp
    │   │   └── main_server.hpp
    │   └── src/
    │       └── main_server.cpp
    └── Utils/
        └── shared_message.hpp

</details>

<!-- 
R-Type-Game/
|-- assets/
| |-- images/
| |-- sounds/
|-- src/
| |-- engine/
| | |-- game_engine.cpp
| | |-- physics_engine.cpp
| | |-- graphics_engine.cpp
| | |-- ...
| |-- game_logic/
| | |-- player.cpp
| | |-- enemy.cpp
| | |-- ...
| |-- networking/
| | |-- server.cpp
| | |-- client.cpp
| |-- ui/
| | |-- menu.cpp
| | |-- hud.cpp
|-- main.cpp
|-- config.ini -->


- **Assets:** This folder contains multimedia resources used in the game, such as animated images (GIFs). These visual resources are used to create in-game elements such as spaceships, projectiles, explosions, etc.

- **Builder:** The builder.sh script is used to automate certain project build tasks. It may contain compilation, installation, or project-specific configuration commands.

- **CMake:** This folder contains configuration files for the CMake build system, which generates the necessary build files for compiling the project.

- **Docker:** The Dockerfile is used to create a Docker image of the project, making it easier to deploy and run the project in a containerized environment.

- **ECS:** This folder contains the source code related to the Entity Component System (ECS) of the game. It is organized into sub-folders for components and systems of the game.

- **GUI:** This folder contains the source code for the game client's user interface (UI). It is organized into sub-folders for different aspects of the UI, such as audio, rendering, entities, etc.

- **Images:** This folder contains images or other visual resources that are not directly tied to the source code but can be used in documentation or for other purposes.

- **R-TYPE_DEV_DOCUMENTATION:** As described earlier, this folder contains all the necessary files for online documentation, such as Markdown files for documentation and MkDocs configuration files.

- **Server:** This folder contains the source code for the game server. It is organized into sub-folders for header files (include) and source files (src) of the server.

- **Utils:** This folder contains utility or shared files that can be used in multiple parts of the project. For example, the shared_message.hpp file could contain definitions of messages shared between the client and the server.

<!-- - **assets:** Contains game assets such as images and sounds.
- **src:** Houses the C++ source code organized by modules and components.
- **engine:** Contains core game engine components.
- **game_logic:** Includes game-specific logic for players, enemies, and objects.
- **networking:** Handles networking and multiplayer functionality.
- **ui:** Manages the user interface components. -->

## Classes
### Core

#### Description :
 La classe Core représente le cœur du système du jeu. Elle est responsable de la gestion de la logique principale du jeu.

#### Méthodes Principales :

    Core(): Constructeur de la classe.
    ~Core(): Destructeur de la classe.
    run(std::string port, std::string ip): Méthode pour exécuter le jeu en spécifiant le port et l'adresse IP.

#### Exemple d'Utilisation :

    cpp

    Core gameCore;
    gameCore.run("12345", "127.0.0.1");

### AComponent

#### Description :
 La classe AComponent est une classe de base abstraite pour les composants du jeu. Elle sert de classe de base pour d'autres classes de composants.

### Entity

#### Description :
 La classe Entity représente une entité dans le jeu. Une entité est un objet du jeu qui peut avoir différents composants attachés.

#### Méthodes Principales :

    Entity(size_t id): Constructeur de la classe avec un identifiant unique.
    ~Entity(): Destructeur de la classe.
    AddComponent(Params&&... args): Méthode pour ajouter un composant à l'entité.
    RemoveComponent(): Méthode pour supprimer un composant de l'entité.
    hasComp(): Méthode pour vérifier si l'entité a un composant donné.
    getComponent(): Méthode pour obtenir un composant spécifique de l'entité.
    nbComps(): Méthode pour obtenir le nombre de composants attachés à l'entité.

#### Exemple d'Utilisation :

    cpp

    Entity playerEntity(1);
    playerEntity.AddComponent<Position>(10.0f, 20.0f);
    if (playerEntity.hasComp<Position>()) {
        auto positionComponent = playerEntity.getComponent<Position>();
        // Utilisation du composant de position
    }

### EntityManager

### Description :
 La classe EntityManager est responsable de la gestion des entités du jeu, de leur création et de leur destruction.

### Méthodes Principales :

    EntityManager(): Constructeur de la classe.
    ~EntityManager(): Destructeur de la classe.
    removeElement(Entity valueToRemove): Méthode pour supprimer une entité de la liste.
    createEntity(): Méthode pour créer une nouvelle entité.
    DestroyEntity(Entity id): Méthode pour détruire une entité par son identifiant.
    getEntityById(size_t id): Méthode pour obtenir une entité par son identifiant.
    getEntities(): Méthode pour obtenir la liste des entités.

#### Exemple d'Utilisation :

    cpp

    EntityManager entityManager;
    Entity playerEntity = entityManager.createEntity();
    entityManager.DestroyEntity(playerEntity.getId());


### ShootingStar

#### Description :
 La classe ShootingStar représente une étoile filante dans le jeu. Une étoile filante se déplace à travers l'écran avec une vitesse donnée et peut être mise à jour et dessinée.

#### Méthodes Principales :

    ShootingStar(float windowWidth, float windowHeight): Constructeur de la classe qui prend la largeur et la hauteur de la fenêtre du jeu comme paramètres.
    void update(float deltaTime): Méthode pour mettre à jour la position de l'étoile filante en fonction du temps écoulé depuis la dernière mise à jour.
    void draw(sf::RenderWindow& window): Méthode pour dessiner l'étoile filante sur la fenêtre du jeu.
    bool isFinished() const: Méthode pour vérifier si l'étoile filante a terminé son trajet.

#### Exemple d'Utilisation :

    cpp

    ShootingStar star(800.0f, 600.0f);
    star.update(0.1f); // Mettre à jour la position de l'étoile filante
    if (star.isFinished()) {
        // L'étoile filante a terminé son trajet
    }

### Star

#### Description :
 La classe Star représente une étoile dans le jeu. Les étoiles sont des objets statiques qui peuvent être mises à jour et dessinées.

#### Méthodes Principales :

    Star(float windowWidth, float windowHeight, float depth): Constructeur de la classe qui prend la largeur et la hauteur de la fenêtre du jeu, ainsi que la profondeur de l'étoile comme paramètres.
    void update(float deltaTime): Méthode pour mettre à jour l'étoile en fonction du temps écoulé depuis la dernière mise à jour.
    void draw(sf::RenderWindow& window): Méthode pour dessiner l'étoile sur la fenêtre du jeu.
    sf::Vector2f getPosition() const: Méthode pour obtenir la position actuelle de l'étoile.

#### Exemple d'Utilisation :

    cpp

    Star star(800.0f, 600.0f, 1.0f);
    star.update(0.1f); // Mettre à jour l'étoile
    sf::Vector2f position = star.getPosition();

## Code Conventions and Best Practices

To maintain code quality and consistency, we follow these coding conventions and best practices:

- C++ code adheres to industry-standard coding practices.
- Meaningful variable and function names.
- Extensive use of comments and documentation.
- Unit tests for critical components.
- Git version control with clear commit messages.
- Code reviews for contributions to ensure quality and conformity.

By adhering to these conventions and best practices, we ensure that the codebase remains maintainable and welcoming to new developers.

## Tutorials and How-To's

To help you get started with contributing to the R-TYPE project in C++, we've prepared a set of tutorials and how-to guides. These resources will walk you through common development tasks and provide step-by-step instructions.

- [How to Implement a New Enemy Type](tutorials/enemy_creation.md)
- [Setting Up Multiplayer and Networking](tutorials/multiplayer_setup.md)
- [Adding New Game Levels](tutorials/level_design.md)

## Contribution Guidelines

We welcome contributions from C++ developers who are passionate about enhancing the R-TYPE game. Before you start, please review our [contribution guidelines](CONTRIBUTING.md) to understand our processes and expectations.

