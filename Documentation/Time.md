[Accueil](Home)  

## Présentation

Le namespace `Time` (`Core/Time.h`) permet de récupérer des informations sur le temps dans l'application.  

## Variables
**`Time`**  
- `static float timeScale` (Valeur par défaut: `1.f`): Echelle de temps appliquée a `deltaTime`.  

## Fonctions
Toutes les fontions sont dans le namespace `Time`.  
**Système**  
- [`void UpdateTime`](#updatetime-1)  

**Getters**  
- [`float Time`](#time-1)  
- [`flaot DeltaTime`](#deltatime-1)  
- [`float UnscaledDeltaTime`](#unscaleddeltatime-1)  
- [`float FixedDeltaTime`](#fixeddeltatime-1)  

---

### <h3 id="UpdateTime">UpdateTime</h3>
```c++ 
void UpdateTime();
```  
Permet de mettre a jour certains éléments de `Time`. Ne devrait pas avoir a être appelée car déjà appelée par `App::run`.  

---

### <h3 id="Time">Time</h3>
```c++ 
float Time();
```  
Permet d'e charger et sauvegarder dans un fichier nommé `fileName` les différents inputs présents dans l'Input System'obtenir le temps en secondes écoulé depuis le lancement de l'application.  

---

### <h3 id="DeltaTime">DeltaTime</h3>
```c++
float DeltaTime();
```
Permet d'obtenir la durée écoulée entre la frame actuelle et la frame précédente, affectée par `timeScale`.  

---

### <h3 id="UnscaledDeltaTime">UnscaledDeltaTime</h3>
```c++
float UnscaledDeltaTime();
```
Permet d'obtenir la durée écoulée entre la frame actuelle et la frame précédente, non affectée par `timeScale`.  

---

### <h3 id="FixedDeltaTime">FixedDeltaTime</h3>
```c++
float DeltaTime();
```
Permet d'obtenir la durée entre chaque update de la physique et appels a `FixedUpdate`.  

---

[Haut de la page](#présentation)  