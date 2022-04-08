[Accueil](Home)  

## Présentation

Le header `Time.h` (`Core/Time.h`) permet de récupérer des informations sur le temps dans l'application et de le manipuler plus facilement.  

## Sommaire

- [Classes](#classes-1)  
- [Variables](#variables-1)  
- [Fonctions](#fonctions-1)  

## <h2 id="Classes">Classes</h2>

- [`class Timer`](#timer-1)  
- [`struct Stopwatch`](#stopwatch-1)  

---

### <h3 id="Timer">Timer</h3>
```c++
class Timer
{
public:
	Timer() = default;
	Timer(float duration, bool looping = false);

	bool hasEnded = false;

	void Update();
	void Restart(float duration = 0.f, bool looping = false);
private:
	float maxTime = 0.f;
	float time = 0.f;
	bool isLooping = false;
};
```
La classe `Timer` permet d'effectuer des comptes a rebours.  

**Variables**  
- `public: bool hasEnded = false`: Devient `true` si le compte a rebours est terminé. Si `isLooping` est égal a `true`, `hasEnded` sera égal a `true` uniquement pendant la frame ou le timer s'est fini, puis il repassera a `false`.  

- `private: bool isLooping = false`: définit si le timer doit recommencer une fois terminé.  

- `private: float maxTime = 0.f`: définit la durée du compte a rebours.  

- `private: float time = 0.f`: définit la durée actuelle du timer.  

**Functions**  
- `public: Timer(float duration, bool looping = false)`: permet d'initialiser le timer avec des valeurs par défaut. `duration` représente la durée du timer, `looping` définit si le timer doit se répéter après s'être terminé.  

- `public: void Update()`: permet d'update les valeurs du timer. Doit être appelé une seule fois par frame.  

- `public: void Restart(float duration = 0.f, bool looping = false)`: Permet de relancer le timer avec de nouvelles valeurs. `duration` représente la durée du timer, `looping` définit si le timer doit se répéter après s'être terminé.  

---
### <h3 id="Stopwatch">Stopwatch</h3>
```c++
struct Stopwatch
{
	Stopwatch() {};

	void Update() { time += Time::DeltaTime(); };

	float time = 0.f;
};
```
La structure `Stopwatch` permet de chronométrer une durée.  

- `void Update()`: permet de mettre a jour le chronomètre. Doit être appelé une seule fois par frame.  

- `float time = 0.f`: durée écoulée depuis le lancement du chronomètre.  

## <h2 id="Variables">Variables</h2>
**`namespace Time`**  
- `static float timeScale` (Valeur par défaut: `1.f`): Echelle de temps appliquée a `deltaTime`.  
- `static int targetFramerate` (Valeur par défaut: `60`): Nombre de frames par seconde visées.  

## <h2 id="Fonctions">Fonctions</h2>
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