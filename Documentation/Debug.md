[Accueil](Home)  

## Présentation

`Debug.h` est un header contenant des macros utiles pour logger des évènements dans un fichier ou 
dans la console avec plus de détails qu'un log/assert normal. 

## Sommaire

- [Enums](#enums-1)  
- [Macros](#macros-1)  
- [Fonctions](#fonctions-1)  

## <h2 id="Enums">Enums</h2>
**`LogSeverity`:**
```c++
enum class LogSeverity
{
	LOG_MESSAGE,
	LOG_WARNING,
	LOG_ERROR,
	LOG_ASSERT,

};
```  
`LogSeverity` sert a donner a [`HD_LOG`](#hd_log-1) la gravité du log.  

## <h2 id="Macros">Macros</h2>
- [`HD_LOG`](#hd_log-1)  
- [`HD_ASSERT`](#hd_assert-1)  

---

### <h3 id="Hd_Log">HD_LOG</h3>
```c++ 
#define HD_LOG(logContent, severity) Debug::Log(logContent, severity, __LINE__, __TIME__, __FILE__)
```  
Permet d'écrire un log dans la console, `logContent` est le message du log, `severity` permet de définir s'il s'agit d'un message, d'un warning, d'une erreur ou d'une assertion. Chaque log est reporté dans les logs de l'application. Wrapper de [`Debug::Log`](#log-1) permettant d'éviter d'écrire le numéro de ligne, le fichier etc...  

---

### <h3 id="Hd_Assert">HD_ASSERT</h3>
```c++ 
#define HD_ASSERT(condition, message) Debug::Assert(condition, message, __LINE__, __TIME__, __FILE__)
```  
Permet d'effectuer une assertion avec un message, contrairement a `assert()` de `<cassert>`, et de l'écrire dans les logs de l'application. Wrapper de la fonction [`Debug::Assert`](#assert-1) permettant d'éviter d'écrire le numéro de ligne, le fichier etc...  

---

## <h2 id="Fonctions">Fonctions</h2>
- [`void Debug::Log`](#debuglog-1)  
- [`void Debug::Assert`](#debugassert-1)  

### <h3 id="DebugLog">Debug::Log</h3>
```c++ 
void Log(const std::string& str, const LogSeverity severity, const int line = 0, const std::string time = "", const std::string filePath = "");
```  
Permet d'écrire un log dans la console, `str` est le message du log, `severity` permet de définir s'il s'agit d'un message, d'un warning, d'une erreur ou d'une assertion. Chaque log est reporté dans les logs de l'application.  

---

### <h3 id="DebugAssert">Debug::Assert</h3>
```c++ 
void Assert(bool condition, const std::string& message, const int line = 0, const std::string time = "", const std::string filePath = "");
```  
Permet d'effectuer une assertion avec un message, contrairement a `assert()` de `<cassert>`, et de l'écrire dans les logs de l'application.  

---

[Haut de la page](#présentation)  