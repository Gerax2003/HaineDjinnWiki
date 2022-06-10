## Physique
La physique du moteur est réalisée à l'aide de la librairie ReactPhysics3D. J'ai choisi cette librairie car elle semblait plus simple à intégrer que PhysX sans pour autant manquer de fonctionnalités, notamment de par le fait que les objets propres à la librairie ont leur mémoire gérée en interne.  

### PhysicsCommon et PhysicsWorld
Ces objets sont tous les deux des pointeurs stockés dans la scène. `PhysicsCommon` est utilisé pour la création et destruction de tout objet provenant de React, et `PhysicsWorld` représente la scène physique. Ces pointeurs sont statiques car ils doivent donc être accessibles en tout temps, notamment pour la création des colliders et rigidbodies.  

### Rigidbody et colliders
Le moteur implémente les colliders en forme de cube, sphère et capsule de React, ainsi que le Rigidbody. Ils héritent tous de la classe `Component` pour faciliter leur utilisation, et les colliders héritent de la classe `Collider` afin d'éviter les doublons de code et de faciliter l'ajout de nouveaux colliders. Ces classes servent de wrapper des classes de React afin de simplifier leur utilisation mais aussi pour permettre de les modifier dans ImGui comme les autres components. Enfin, les colliders ont besoin d'un rigidbody pour pouvoir être créés. React offre la possibilité de n'utiliser qu'un `CollisionBody` pour palier à ce problème, cependant j'ai jugé que l'intégration de cette classe n'allait pas être utile dans notre cas.  

### Events
Les events arrivent de React à notre moteur via la classe `PhysicsEventListener`, elle hérite de l'`EventListener` de la librairie. Elle récupère depuis les colliders de React passés en paramètres les colliders de notre moteur afin de broadcast leurs évènements respectifs, qui seront récupérés par les game objects concernés pour enfin arriver aux components de ces derniers. Le système d'évènements est assez simple et tient dans les deux classes `Event` et `EventSubscriber`. Les paramètres de l'event sont passés sous la forme d'un `void*` pour permettre d'envoyer n'importe quel objet en paramètre, ici, une classe dédiée qui contient les deux colliders ainsi que des informations supplémentaires sur l'évèenement.  

## Exemple
![phys_test](uploads/aec5d3909d04d778c958467d0a9e9c50/phys_test.gif)  
Ce gif provient de la scène de tests physiques, `phys_test`. Les colliders peuvent être contrôlés à l'aide d'un component possédé par tous les objets qui bougent, les contrôles sont affichés dans l'éditeur du component.  