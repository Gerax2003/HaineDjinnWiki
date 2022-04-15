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

**Resource search**  
- [int SearchResource(const std::string filePath, const ResourceType type)](#searchresource-1)  
- [void BindResource(int index, const ResourceType type, bool bindDefault = false)](#bindresource-1)  
- [void CheckResourcesState(const ResourceType type)](#checkresourcesstate-1)  

**Queue destruction**  
- [void ResetResources()](#resetresources-1)  
- [void EraseQueue()](#erasequeue-1)  
- [void CleanQueue()](#cleanqueue-1)  

**Resource creation**  
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

Looks for a resource with the path `filePath` in the deque corresponding to `type`.  

## <h3 id="BindResource">BindResource</h3>
```c++
	void BindResource(int index, const ResourceType type, bool bindDefault = false);
```

Binds the resource in the deque corresponding to `type` at a given `index`. If `bindDefault` is true, binds OpenGL's default.  

## <h3 id="CheckResourcesState">CheckResourcesState</h3>
```c++
	void CheckResourcesState(const ResourceType type);
```

Checks in the deque corresponding to `type` if the resources stored are initialized in OpenGL and initializes them if not initialized.  

## <h3 id="ResetResources">ResetResources</h3>
```c++
	void ResetResources();
```

Clears all resources deques as well as resources to load.  

## <h3 id="EraseQueue">EraseQueue</h3>
```c++
	void EraseQueue();
```

Clears the resources waiting to be loaded.  

## <h3 id="CleanQueue">CleanQueue</h3>
```c++
	void CleanQueue();
```

Clears the resources already loaded still in the loading queue.  

## <h3 id="AddToLoad">AddToLoad</h3>
```c++
	void* AddToLoad(const std::string filePath, const ResourceType type);
```

Adds to the loading queue a resource located at `filePath` of type `type`. Returns a `void*`, needs to be casted as a `std::shared_ptr<TypeClass>`.  

---

[Haut de la page](#présentation)  