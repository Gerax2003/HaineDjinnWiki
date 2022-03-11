[Accueil](Home)  

## Présentation

L'Input System (`Game/InputSystem.h`) permet d'utiliser les fonctions d'inputs clavier de GLFW depuis n'importe quel endroit du code et d'une façon simplifiée, avec une utilisation inspirée de Unity. 

## Fonctions

- [`void SetWindow(GLFWwindow* inWindow);`]()
- [`void LoadInputs(const std::string& fileName);`]()
- [`void SaveInputs(const std::string& fileName);`]()
- [`float GetAxis(const std::string& axis);`]()
- [`bool GetInput(const std::string& input);`]()
- [`bool GetInputDown(const std::string& input);`]()