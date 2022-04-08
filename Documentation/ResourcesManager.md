[Accueil](Home)  

## Présentation

`ResourcesManager.h` est un header contenant la classe `ResourcesManager`, qui centralise et gère  le chargement/déchargement de resources afin d'éviter les doublons.  

## Sommaire

- [Variables](#variables-1)  
- [Méthodes](#méthodes-1)  

## <h2 id="Variables">Variables</h2>

- `private: std::deque<Resource*> toLoad`: This `std::deque` stores temporary resources used as a task list by the resources manager.  

-
```c++
private: 
	std::deque<std::shared_ptr<Material>> materials;
	std::deque<std::shared_ptr<Texture>> textures;
	std::deque<std::shared_ptr<Mesh>> meshes; 
	std::deque<std::shared_ptr<Shader>> shaders;
```
These `std::deque` are used to store resources and can only be accessed through `ResourcesManager`'s methods.  

- `bool runThreads = false`: used to enable/disable multithreaded loading (Not Implemented yet)  

## <h2 id="Méthodes">Méthodes</h2>



---

[Haut de la page](#présentation)  