

[Accueil](Home.md)  

Interface système: OpenGL, Vulkan, DirectX 12  

   - Vulkan: Vulkan est une API très flexible, mais une connaissance accrue est nécessaire afin de l'utiliser correctement. Dans ce projet, nous avons jugé qu'il serait un désavantage de temps et d'optimisation.
   - DirectX 12: C'est un point partagé notamment avec Directx 12.
   - **OpenGL(4.5)**: Dans ce projet, nous utiliserons l'API de OpenGL. Nous avons de très bonne connaissance sur celle-ci et de plus, il ce trouve qu'elle est énormément documenté sur Internet. Elle est plus que suffisante pour pouvoir faire un moteur.

Editor: ImGUI, FLTK(Fast Light Tool Kit), WxWidgets   
   - FLTK: Librairie multi-plateforme et simple d'usage
   - WxWidget: Donne aux applications une apparence véritablement native car elle utilise l'API native de la plate-forme plutôt que d'émuler l'interface graphique. Elle est complète et open-source.
   - **ImGUI**: une lib très connu et donc beaucoup de documentations et d’extensions, qui nous serons très utiles pour avoir une bonne UI dans le moteur. ImGUI intègre également un IO qui peut retourner le temps, le deltatime, les inputs basiques, etc… Ce qui est un gain de temps.  

Sound: irrKlang, Superpowered Audio SDK, FMOD  
   - **irrKlang**: La librairie s'adapte à un espace 2D comme 3D, elle sait lire de nombreux fichier audio (MP4, wav,...), elle est Cross-Plateforme, elle possède toutes les fonctionnalités connues des bibliothèques audio de bas niveau ainsi que de nombreuses fonctionnalités utiles comme un moteur de streaming sophistiqué, une lecture audio extensible, ...
   - Superpowered: Est surtout utilisé pour les téléphones.
   - FMOD: Est une librairie où on peut modifier les sons. FMOD Core a subi des optimisations majeures dans le mixage, le rééchantillonnage, le décodage et le traitement des effets.  
  
System interface: GLFW, SDL  
   - SDL: Est une bibliothèque permettant de gérer des pointeurs de fonction OpenGL.
   - **GLFW**: C'est une API qu'on a utilisé à maintes reprises, et qui comme OpenGL est très bien documenté, elle est simple à implémenter.  

3DModel Loading: ASSIMP, TinyObj    
   - TinyObj: est malheureusement trop limité pour notre moteur. Elle ne prend en compte que les .obj qui sont des fichiers rarement utilisés dans le jeu vidéo.
   - **ASSIMP**: Pour la partie 3D et chargement de model, on prendra **ASSIMP** car elle prend en compte plusieurs type d'objet 3D(FBX, OBJ, 3DMAX, ...), on peut notamment implémenter des animations ce qui sera très pratique pour la suite.  

Physique: PhysX, JoltPhysics, qu3e, ReactPhysics3D    
   - PhysX: bien que très complète, documentée et utilisée, trop difficile a intégrer et utiliser pour le peu de temps restant au moment de l'intégration surtout vu le niveau de détail physique qui nous est nécessaire pour le jeu.  
   - JoltPhysics: très complète et orientée multithreading et fiable puisque utilisée pour Horizon Forbidden West et semble plus simple que PhysX, cependant toujours trop pour notre projet.  
   - qu3e: librairie facile d'utilisation et d'intégration mais ne peut faire que de la simulation de cubes.  
   - **ReactPhysics3D**: librairie assez complète et facile a intégrer, multi plateformes et bien documentée, et offre des collisions entre assez de primitives pour notre projet.  
