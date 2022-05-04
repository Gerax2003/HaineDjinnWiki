[Accueil](Home)  

## Présentation

`ResourcesManager.h` est un header contenant la classe `ResourcesManager`, qui centralise et gère  le chargement/déchargement de resources afin d'éviter les doublons.  

## Sommaire

- [Variables](#variables-1)  
- [Méthodes](#méthodes-1)  

## <h2 id="Variables">Variables</h2>

- `private: std::deque<Resource*> toLoad`: Cette `std::deque` stocke temporairement les ressources a charger, 'sert de liste de taches' au ResourcesManager.  

-
```c++
private: 
	std::deque<std::shared_ptr<Material>> materials;
	std::deque<std::shared_ptr<Texture>> textures;
	std::deque<std::shared_ptr<Mesh>> meshes; 
	std::deque<std::shared_ptr<Shader>> shaders;
```
Ces `std::deque` stockent les resources et ne peuvent être accédées que par les méthodes de `ResourcesManager`.  

- `bool runThreads = false`: active/désactive le chargement multithreadé (Pas encore implémenté)  

## <h2 id="Méthodes">Méthodes</h2>

**Recherche de ressources**  
- [int SearchResource(const std::string filePath, const ResourceType type)](#searchresource-1)  
- [void BindResource(int index, const ResourceType type, bool bindDefault = false)](#bindresource-1)  
- [void CheckResourcesState(const ResourceType type)](#checkresourcesstate-1)  

**Destruction de la queue**  
- [void ResetResources()](#resetresources-1)  
- [void EraseQueue()](#erasequeue-1)  
- [void CleanQueue()](#cleanqueue-1)  

**Création de ressources**  
- [void* AddToLoad(const std::string filePath, const ResourceType type)](#addtoload-1)  
- [void LoadResource(const std::string filePath, const ResourceType type)](#loadresource-1)  
- [void CreateResource(const std::string filePath, const ResourceType type)](#createresource-1)  
- [void DestroyResource(const int index, const ResourceType type)](#destroyresource-1)  

**Getters**  
- [size_t GetArraySize(ResourceType type)](#getarraysize-1)   
- [int GetShaderProgram(const std::string& name)](#getshaderprogram-1)  
- [int GetBufferSize(const std::string& name)](#getbuffersize-1)  

## <h3 id="SearchResource">SearchResource</h3>
```c++
	int SearchResource(const std::string filePath, const ResourceType type);
```

Cherche une ressource qui a le chemin `filePath` dans la `std::deque` correspondant a `type`.  

## <h3 id="BindResource">BindResource</h3>
```c++
	void BindResource(int index, const ResourceType type, bool bindDefault = false);
```

Binds la ressource de la deque correspondant a `type` a l'index `index`. si `bindDefault` est true, binds l'option par défaut d'OpenGL.  

## <h3 id="CheckResourcesState">CheckResourcesState</h3>
```c++
	void CheckResourcesState(const ResourceType type);
```

Vérifie dans la deque correspondant a `type` si les ressources sont initialisées dans OpenGL et si elles ne le sont pas, les initialise.  

## <h3 id="ResetResources">ResetResources</h3>
```c++
	void ResetResources();
```

Clear toutes les deque ainsi que la file d'attente.  

## <h3 id="EraseQueue">EraseQueue</h3>
```c++
	void EraseQueue();
```

Clear la file d'attente.  

## <h3 id="CleanQueue">CleanQueue</h3>
```c++
	void CleanQueue();
```

Clear les ressources déja chargées toujours présentes dans la queue.  

## <h3 id="AddToLoad">AddToLoad</h3>
```c++
	// Mesh/Texture/Shader overload
	void* AddToLoad(const std::string filePath, const ResourceType type);
        // Material overload
	void* AddToLoad(const std::string name, const std::string diffTexPath, const std::string normTexPath, Vector4 ambientColor = { 1.f, 1.f, 1.f, 1.f }, Vector4 diffuseColor = { 1.f, 1.f, 1.f, 1.f }, Vector4 specularColor = { 1.f, 1.f, 1.f, 1.f });
```

Ajoute a la file d'attente une ressource située au chemin `filePath` du type `type`. Renvoie un `void*`, qui doit être casté en tant que `std::shared_ptr<TypeClass>`. La deuxiême fonction ne sert qu'aux ressources de classe `Material`.    

## <h3 id="LoadResource">LoadResource</h3>
```c++
	void LoadResource(const std::string filePath, const ResourceType type);
```

Crée une resource située au chemin `filePath` de type `type` si elle n'est pas déja créée.  

## <h3 id="CreateResource">CreateResource</h3>
```c++
	void CreateResource(const std::string filePath, const ResourceType type);
```

Crée une resource située au chemin `filePath` de type `type`. Ne vérifie pas les doublons.  

## <h3 id="DestroyResource">DestroyResource</h3>
```c++
	void DestroyResource(const int index, const ResourceType type)
```

Détruit une ressource de type `type` située a l'index `index` dans la deque correspondante.  

## <h3 id="GetArraySize">GetArraySize</h3>
```c++
	size_t GetArraySize(ResourceType type);
```

Renvoie la taille de la deque correspondant a `type`.  

## <h3 id="GetShaderProgram">GetShaderProgram</h3>
```c++
	int GetShaderProgram(const std::string& name);
```

Renvoie l'index dans OpenGL du shader nommé `name`.  

## <h3 id="GetBufferSize">GetBufferSize</h3>
```c++
	int GetBufferSize(const std::string& name);
```

Renvoie le nombre de vertices du mesh nommé `name`.  


---

[Haut de la page](#présentation)  