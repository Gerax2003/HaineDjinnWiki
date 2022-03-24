[Accueil](Home)  

**UML** : https://lucid.app/lucidchart/a6b6cdfc-34dc-4066-b307-bcc093a05207/edit?invitationId=inv_db76af16-e388-40a6-b782-dfb8ddd5c616  

## Classes

```c++
class MyClass
{
private:
    MyClass(int _position, float _angle) {position = _position; angle = _angle;}
    ~MyClass();
    
    int position = 0;
    float angle = 0.f;
public:
    void AntoineDaniel();
    void Ponce();
};
```

## Structures

```c++
struct MyStruct
{
    unsigned int never = 0;
    unsigned int gonna = 0;

    float give = 0.f;
    float you = 0.f;
    float up = 0.f;

    char* Rick() {return "Astley";}
};
```

## Enums
```c++
enum Jours {
    DIMANCHE, LUNDI, MARDI, MERCREDI, JEUDI, CHIMPANZE, VENDREDI, SAMEDI
};
```

## Appel d'une Class Component

```c++
class Component
{
private:
    Component();
    ~Component();

    Component CreateComponent() { return new Component; };
    Component GetComponentInParent() {};
    Component GetComponentInChildren() {};
};
```

## Namespace

```c++
namespace Maths
{
    class SuiteNumerique
    {

    };

    void GeneralMaths();
    mat4x4 Multiplication();

    int temp = 0;
}
```

## Macros
```
#define PI          3.1415f
#define GRAVITY	    9.81f 
#define IS_EDITOR   true
```

## Git

> Une branche par feature. Avec une branche Dev. (git flow)
