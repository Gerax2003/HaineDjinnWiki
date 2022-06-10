# Introduction
<p>Pour inclure des animations/skeletal animation dans notre moteur, j'ai implémenté Assimp. L’avantage de cette librairie est qu’elle peut charger un fichier modèle contenant un maillage, un squelette et un/des animation(s). L'architecture actuelle du système d'animation est inspirée du tutoriel de learnopengl.com.</p>

# La description:
<p>A l'implémentation des animations, l’architecture du moteur devait être complètement revue car celle-ci ne pouvait pas fonctionner avec le chargement d' objets et de la gestion de l’éditeur.
Au chargement de l’objet, on vérifie si l’objet en question possède oui ou non des animations, c’est à ce moment qu’elles sont chargées. Dès que le component “animator” est sur l’objet vous allez pouvoir sélectionner l’animation que vous voulez. L’update de l’animation est calculé dans Animator::UpdateAnimation(double dt), appelé dans Renderer.cpp.</p>

# Fichiers:
### Stockage et calcules:

- Renderer/include/Renderer/Animation.h  
   - Charge et stock les bones.  
- Renderer/include/Renderer/Animator.h  
   - Update position bone/animation squelette.  
   - Animator est une classe qui stock un vecteur de 100 os basé sur le squelette du SkeletalMesh qui sera envoyé au Vertex Shader.

### Shader Animation:  

- Assets/Shaders/animation.vert  
   - un shader servant à dessiner soit des modèles statiques, soit des modèles animés,  
- Assets/Shaders/animation.frag  
