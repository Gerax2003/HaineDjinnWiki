[Accueil](Home)  

## Présentation

L'Input System (`Game/InputSystem.h`) permet d'utiliser les fonctions d'inputs clavier de GLFW depuis n'importe quel endroit du code et d'une façon simplifiée, avec une utilisation inspirée de Unity. 

## Fonctions

- [`void SetWindow`](#SetWindow)  
- [`void LoadInputs / void SaveInputs`](#LoadSave)  
- [`float GetAxis`](#Axis)  
- [`bool GetInput`](#Input)  
- [`bool GetInputDown`](#InputDown)  
- [`bool GetMouseButton`](#MouseButton)  
- [`bool GetMouseButtonDown`](#MouseDown)  
---
### <h3 id="SetWindow">SetWindow</h3>
```c++ 
void SetWindow(GLFWwindow* inWindow);
```  
Permet de donner a l'l'Input System un pointeur `inWindow` sur la fenêtre utilisée, appelée dans le constructeur de la class `App`.  

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