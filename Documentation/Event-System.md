[Accueil](Home.md)  

## Présentation

L'IEvent System regroupe deux classes `Event` et `EventSubscriber`(`Core/Event.h` et `Core/EventSubscriber.h`). Les `EventSubscriber` stockent un pointeur sur fonction dont la signature est `void(void*)` et sont abonnés à un `Event`. Quand la fonction `Broadcast` de l'Event est appelée, la fonction de tous les subscribers est appelée avec les mêmes paramètres. 

## Variables

- `private: EventSubscriber::std::function<void(void*)> function`: Pointeur sur la fonction du subscriber, initialisée par la fonction `SetFunction(std::function<void(void*)> inFunction)`.  

- `private: EventSubscriber::Event* subEvent = nullptr`: pointeur sur l'évènement auquel le subscriber est abonné. Initialisé par la fonction `Subscribe(Event* event)`.  

- `private: Event::std::deque<EventSubscriber*> subscribers`: Liste de tous les abonnés à cet évènement. Ajout d'un abonné via l'appel de `AddSubscriber(EventSubscriber* subscriber)` et retrait via l'appel de `Unsubscribe(EventSubscriber* subscriber)`.  

## Fonctions

```c++
	void Event::Broadcast(void* parameters);
```
Cette fonction permet de lancer l'évènement à tous les abonnés de l'event.  

---
```c++
	void Event::AddSubscriber(EventSubscriber* subscriber);
```
Cette fonction permet d'ajouter un abonné à l'event.  

---
```c++
	void Event::Unsubscribe(EventSubscriber* subscriber);
```
Cette fonction permet retirer un abonné à l'event.  

---
```c++
	void EventSubscriber::Subscribe(Event* event);
```
Cette fonction permet d'abonner le subscriber à un event.  

---
```c++
	void EventSubscriber::SetFunction(std::function<void(void*)> inFunction);
```
Cette fonction permet définir la fonction appelée par l'abonné.  

---

[Haut de la page](#présentation)