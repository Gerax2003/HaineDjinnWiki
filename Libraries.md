

[Homepage](Home)  

Editor: ImGui, FLTK(Fast Light Tool Kit), WxWidgets   
<ul>
   <li>ImGUI: Connaissance élevé de la librairie</li>
   <li>FLTK: Librairie multi-plateforme et simple d'usage</li>
   <li>WxWidget: Donne aux applications une apparence véritablement native car elle utilise l'API native de la plate-forme plutôt que d'émuler l'interface graphique. Elle est complète, open-source et mature. </li></ul>  


> On a choisi de prendre IMGUI, car cette une librairie sur laquelle on a eu l'habitude de travailler. Elle est assez complete et plus optimisé que les autres librairies cités.  

Sound: irrKlang, Superpowered Audio SDK, FMOD  
<ul>
   <li>irrKlang: La librairie s'adapte à un espace 2D comme 3D, elle sait lire de nombreux fichier audio (MP4, wave,...), elle est Cross-Plateforme, elle possède toutes les fonctionnalités connues des bibliothèques audio de bas niveau ainsi que de nombreuses fonctionnalités utiles comme un moteur de streaming sophistiqué, une lecture audio extensible, ...</li>
   <li>Superpowered: Est surtout utilisé pour les téléphones</li>
   <li>FMOD: Est une librairie pour faire nos propre sons, ont peux mdifier de plein de facon. FMOD Core a subi des optimisations majeures dans le mixage, le rééchantillonnage, le décodage et le traitement des effets.</li></ul>  


> On a choisi la librairie ...
  
System interface: GLFW, EPOXY, bgfx  
<ul>
   <li>GLFW: Grande connaissance de la librairie</li>
   <li>Epoxy: Est une bibliothèque permettant de gérer des pointeurs de fonction OpenGL.</li>
   <li>bgfx: Bibliothèque de rendu de style multiplateforme, indépendante de l'API graphique, sous licence open source BSD-2 clause permissive. Il est possible de l'utiliser avec SDL, GLFW et des bibliothèques de fenêtrage multiplateformes similaires.</li></ul>


> On a choisi GLFW, car c'est une librairie qu'on a énormément utilisé, c'est un avantage de rapidité.  

3DModel Loading: ASSIMP,  
> Pour la partie 3D et chargement de model, on prendra ASSIMP car elle prend en compte plusieurs type d'objet 3D(FBX, OBJ, 3DMAX, ...), on peut notamment implémenter des animations ce qui sera très pratique.  