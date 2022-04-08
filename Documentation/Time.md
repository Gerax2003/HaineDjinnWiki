[Accueil](Home)  

## Présentation

Le namespace `Time` (`Core/Time.h`) permet de récupérer des informations sur le temps dans l'application.  

## Variables
**`Time`**  
- `static float timeScale` (Valeur par défaut: `1.f`): Echelle de temps appliquée a `deltaTime`.  
- `static int targetFramerate` (Valeur par défaut: `60`): Nombre de frames par seconde visées.  

## Fonctions
Toutes les fontions sont dans le namespace `Time`.  
**Système**  
- [`void Update`](#update-1)  

**Getters**  
- [`double Time`](#time-1)  
- [`double DeltaTime`](#deltatime-1)  
- [`double UnscaledDeltaTime`](#unscaleddeltatime-1)  
- [`double FixedDeltaTime`](#fixeddeltatime-1)  

---

### <h3 id="Update">Update</h3>
```c++ 
void Update();
```  
Permet de mettre a jour certains éléments de `Time`. Ne devrait pas avoir a être appelée car déjà appelée par `App::run`.  

---

### <h3 id="Time">Time</h3>
```c++ 
double Time();
```  
Permet d'obtenir la durée d'exécution du programme.  

---

### <h3 id="DeltaTime">DeltaTime</h3>
```c++
double DeltaTime();
```
Permet d'obtenir la durée écoulée entre la frame actuelle et la frame précédente, affectée par `timeScale`.  

---

### <h3 id="UnscaledDeltaTime">UnscaledDeltaTime</h3>
```c++
double UnscaledDeltaTime();
```
Permet d'obtenir la durée écoulée entre la frame actuelle et la frame précédente, non affectée par `timeScale`.  

---

### <h3 id="FixedDeltaTime">FixedDeltaTime</h3>
```c++
double FixedDeltaTime();
```
Permet d'obtenir la durée entre chaque update de la physique et appels a `FixedUpdate`.  

---

[Haut de la page](#présentation)  