[Accueil](Home)  

## Présentation

L'IEvent System regroupe deux classes `Event` et `EventSubscriber`(`Core/Event.h` et `Core/EventSubscriber.h`). Les `EventSubscriber` stockent un pointeur sur fonction dont la signature est `void(void*)` et sont abonnés à un `Event`. Quand la fonction `Broadcast` de l'Event est appelée, la fonction de tous les subscribers est appelée avec les mêmes paramètres.  
