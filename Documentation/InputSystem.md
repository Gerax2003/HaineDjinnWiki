[Accueil](Home.md)  

## Présentation

L'Input System (`Game/InputSystem.h`) permet d'utiliser les fonctions d'inputs clavier de GLFW depuis n'importe quel endroit du code et d'une façon simplifiée, avec une utilisation inspirée de Unity. 

## Sommaire

- [Variables](#variables-1)  
- [Fonctions](#fonctions-1)  


## <h2 id="Variables">Variables</h2>
**`InputSystem::Keyboard`**  
- `static std::map<std::string, int> keybinds`: stocke les noms et les inputs liés de tous les inputs du clavier.  
- `static std::map<std::string, std::pair<int, int>> axes`: stocke les noms et les inputs liés de tous les axes du clavier.  

**`InputSystem::Mouse`**  
- `static int mouseButtons[9]`: stocke les 8 macros définissant les 8 boutons de souris gérés par ce dernier. Permet de compter les boutons de 1 a 8 plutot que de 0 a 7.  

## <h2 id="Fonctions">Fonctions</h2>
Toutes les fontions sont dans le namespace `InputSystem`.  
**Système**  
- [`void SetWindow`](#setwindow-1)  
- [`void UpdateSystem`](#updatesystem-1)  
- [`void LoadInputs / void SaveInputs`](#loadinputssaveinputs-1)  

**Inputs clavier**  
- [`float GetAxis`](#getaxis-1)  
- [`bool GetInput`](#getinput-1)  
- [`bool GetInputDown`](#getinputdown-1)  

**Inputs souris**  
- [`bool GetMouseButton`](#getmousebutton-1)  
- [`bool GetMouseButtonDown`](#getmousebuttondown-1)  
- [`Vector2 GetMousePos`](#getmousepos-1)  
- [`Vector2 GetMouseDelta`](#getmousedelta-1)  

---

### <h3 id="SetWindow">SetWindow</h3>
```c++ 
void SetWindow(GLFWwindow* inWindow);
```  
Permet de donner a l'l'Input System un pointeur `inWindow` sur la fenêtre utilisée, appelée dans le constructeur de la class `App`.  

---

### <h3 id="UpdateSystem">UpdateSystem</h3>
```c++ 
void UpdateSystem();
```  
Permet de mettre a jour certains éléments de l'InputSystem. Ne devrait pas avoir a être appelée car déja appelée par `App::run`, appelle aussi `glfwPollEvents()`.  

---

### <h3 id="LoadSave">LoadInputs/SaveInputs</h3>
```c++ 
void LoadInputs(const std::string& fileName);
void SaveInputs(const std::string& fileName);
```  
Permet de charger et sauvegarder dans un fichier nommé `fileName` les différents inputs présents dans l'Input System.  

---

### <h3 id="Axis">GetAxis</h3>
```c++
float GetAxis(const std::string& axis);
```
Permet d'obtenir la valeur actuelle entre -1 et 1 de l'axe `axis`.  

---

### <h3 id="Input">GetInput</h3>
```c++
bool GetInput(const std::string& input);
```
Renvoie l'état actuel de la touche liée a `input`, `true` si la touche est appuyée et `false` si elle ne l'est pas.  

---

### <h3 id="InputDown">GetInputDown</h3>
```c++
bool GetInputDown(const std::string& input);
```
Renvoie `true` si la touche liée a `input` vient d'être appuyée et `false` si la touche n'est pas appuyée ou si elle était déja appuyée.  

---

### <h3 id="MouseButton">GetMouseButton</h3>
```c++
bool GetMouseButton(const unsigned int button);
```
Renvoie l'état actuel du bouton lié a `button`, `true` si le bouton est appuyé et `false` s'il ne l'est pas. `button` doit être entre 1 et 8 inclus.  

---

### <h3 id="MouseDown">GetMouseButtonDown</h3>
```c++
bool GetMouseButtonDown(unsigned int button);
```
Renvoie `true` si le bouton lié a `button` vient d'être appuyé et `false` si le bouton n'est pas appuyé ou s'il était déja appuyé. `button` doit être entre 1 et 8 inclus.  

---

### <h3 id="MousePos">GetMousePos</h3>
```c++
Vector2 GetMousePos();
```
Renvoie la position actuelle du curseur, relative au bord supérieur gauche de la fenêtre.  

---

### <h3 id="MouseDelta">GetMouseDelta</h3>
```c++
Vector2 GetMouseDelta();
```
Renvoie l'écart en pixels de la souris entre sa position actuelle et sa position précédente.  

---

[Haut de la page](#présentation)  