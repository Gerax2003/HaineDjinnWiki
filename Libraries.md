

[Homepage](Home)  

System interface: OpenGL, Vulkan, DirectX 12  
<ul>
   <li>**Vulkan**: Vulkan est une API tres flexible, mais une connaissance accrue est nécessaire afin de l'utiliser correctement. Dans ce pojet, nous avons jugé qu'il serait un désavantage de temps et d'optimisation.</li>
   <li>DirectX 12: C'est un point partagé notamment avec Directx 12.</li>
   <li>OpenGL(4.5): Dans ce projet, nous utiliserons l'API de OpenGL. Nous avons de très bonne connaissance sur celle-ci et de plus, il ce trouve qu'elle est énormément documenté sur Internet. Elle est plus que suffisante pour pouvoir faire un moteur.</li></ul>  

Editor: ImGui, FLTK(Fast Light Tool Kit), WxWidgets   
<ul>
   <li>FLTK: Librairie multi-plateforme et simple d'usage</li>
   <li>WxWidget: Donne aux applications une apparence véritablement native car elle utilise l'API native de la plate-forme plutôt que d'émuler l'interface graphique. Elle est complète et open-source. </li>
   <li>ImGUI: Connaissance élevé de la librairie</li></ul>  


> On a choisi de prendre IMGUI, car cette une librairie sur laquelle on a eu l'habitude de travailler. Elle est assez complete et plus optimisé que les autres librairies cités.  

Sound: irrKlang, Superpowered Audio SDK, FMOD  
<ul>
   <li>irrKlang: La librairie s'adapte à un espace 2D comme 3D, elle sait lire de nombreux fichier audio (MP4, wave,...), elle est Cross-Plateforme, elle possède toutes les fonctionnalités connues des bibliothèques audio de bas niveau ainsi que de nombreuses fonctionnalités utiles comme un moteur de streaming sophistiqué, une lecture audio extensible, ...</li>
   <li>Superpowered: Est surtout utilisé pour les téléphones</li>
   <li>FMOD: Est une librairie où ont peux modifier de plein de facon les sons. FMOD Core a subi des optimisations majeures dans le mixage, le rééchantillonnage, le décodage et le traitement des effets.</li></ul>  


> On a choisi la librairie ...
  
System interface: GLFW, SDL  
<ul>
   <li>SDL: Est une bibliothèque permettant de gérer des pointeurs de fonction OpenGL.</li></ul>
   <li>GLFW: C'est une API qu'on a utilisé à maintes reprises, et qui comme OpenGL est tres bien documenté, elle est simple à implémenter.</li>

3DModel Loading: ASSIMP,  
> Pour la partie 3D et chargement de model, on prendra ASSIMP car elle prend en compte plusieurs type d'objet 3D(FBX, OBJ, 3DMAX, ...), on peut notamment implémenter des animations ce qui sera très pratique.  