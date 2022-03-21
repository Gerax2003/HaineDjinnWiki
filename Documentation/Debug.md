[Accueil](Home)  

## Présentation

`Debug.h` est un header contenant des macros . 

## Enums
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

## Macros
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

## Fonctions
- [`void Debug::Log`](#log-1)  
- [`void Debug::Assert`](#assert-1)  

### <h3 id="Log">Debug::Log</h3>
```c++ 
void Log(const std::string& str, const LogSeverity severity, const int line = 0, const std::string time = "", const std::string filePath = "");
```  
Permet d'écrire un log dans la console, `str` est le message du log, `severity` permet de définir s'il s'agit d'un message, d'un warning, d'une erreur ou d'une assertion. Chaque log est reporté dans les logs de l'application.  

---

### <h3 id="Assert">Debug::Assert</h3>
```c++ 
void Assert(bool condition, const std::string& message, const int line = 0, const std::string time = "", const std::string filePath = "");
```  
Permet d'effectuer une assertion avec un message, contrairement a `assert()` de `<cassert>`, et de l'écrire dans les logs de l'application.  

---

[Haut de la page](#présentation)  