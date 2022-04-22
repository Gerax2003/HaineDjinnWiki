[Accueil](Home)  

## Présentation

`Component.h` est un header contenant la classe `Component`, qui sert de base a toutes les classes qui servent de component, telles que `ModelInstance` ou `Transform`.  

## Sommaire

- [Variables](#variables-1)  
- [Méthodes](#méthodes-1)  

## <h2 id="Variables">Variables</h2>

## <h2 id="Méthodes">Méthodes</h2>

**Resource search**  
- [int SearchResource(const std::string filePath, const ResourceType type)](#searchresource-1)  

## <h3 id="SearchResource">SearchResource</h3>
```c++
	int SearchResource(const std::string filePath, const ResourceType type);
```

Looks for a resource with the path `filePath` in the deque corresponding to `type`.  

---

[Haut de la page](#présentation)  