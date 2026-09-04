# Offensive Security Portfolio

![Status](https://img.shields.io/badge/Status-Active_Project-success)
![Focus](https://img.shields.io/badge/Focus-Web_%7C_Network_%7C_Red_Team-red)
![Goal](https://img.shields.io/badge/Goal-10+_Labs-blue)

Bienvenido a mi repositorio técnico de pentesting ofensivo.

Este repositorio funciona como un **laboratorio vivo y en constante evolución**. Aquí documento mis prácticas, hallazgos y metodologías aplicadas tanto en trabajos académicos de mi formación en Ingeniería (especialización en Ciberseguridad) como en retos de plataformas de práctica como TryHackMe, con el objetivo de desarrollar una sólida base técnica en explotación web, pentesting de infraestructura y Red Team.

## Sobre este proyecto y los Writeups

A diferencia de un repositorio estático, este es un proyecto en desarrollo. Las carpetas `WEB/` y `RED/` contienen informes formales entregados como parte de mis cursos universitarios, siguiendo una guía/metodología de referencia (OWASP/OSSTMM). Las carpetas por plataforma (`TryHackMe/`, y a futuro `HackTheBox/`, etc.) contienen writeups de práctica personal continua, organizados por nivel de dificultad, y seguirán creciendo con nuevos retos.

La dificultad de cada reto de plataforma refleja la calificación oficial de origen:

- 🔵 **Very Easy**
- 🟢 **Easy**
- 🟡 **Medium**
- 🔴 **Hard**
- 🟣 **Insane**

## Aviso

Todas las pruebas se realizaron en entornos aislados y diseñados para práctica de seguridad (máquinas deliberadamente vulnerables desplegadas en laboratorio local, la aplicación web pública de entrenamiento testfire.net, y máquinas de plataformas como TryHackMe). Este material es exclusivamente educativo/académico. No se debe aplicar ninguna de estas técnicas contra sistemas, redes o aplicaciones sin autorización explícita.

## Tabla de Investigaciones

Los casos están divididos por sala/plataforma de origen.

### TryHackMe

Writeups de práctica personal en TryHackMe, organizados por dificultad. Este apartado se irá ampliando a medida que complete nuevas rooms.

| Room | Documento | Dificultad | Descripción breve | Herramientas |
|---|---|---|---|---|
| **LazyAdmin** | `TryHackMe/Easy/LazyAdmin/LazyAdmin-TryHackMe.pdf` | 🟢 Easy | Backup disclosure en SweetRice 1.5.1 con extracción y crackeo de hash MD5, explotación de Arbitrary File Upload para obtener reverse shell, y escalada de privilegios a root vía permiso sudo NOPASSWD sobre un script Perl que invocaba un script shell modificable. | Nmap, wfuzz, searchsploit, CrackStation, Netcat |
| **Grep** | `TryHackMe/Easy/Grep/Grep-TryHackMe.pdf` | 🟢 Easy | Reconocimiento OSINT sobre repositorio de GitHub expuesto (API key filtrada en historial de commits), bypass de validación de archivos (magic bytes) para subir una reverse shell PHP, RCE, y extracción de credenciales desde la base de datos. | Ffuf, Netcat, PHP CLI One-liner, Burp Suite, GitHub Code Search |

### WEB

Informes de pentest en aplicaciones web realizados en el curso **Pentesting en Aplicaciones Web (CBN05)**.

| Documento | Entorno | Descripción breve | Herramientas |
|---|---|---|---|
| `WEB/pentest-web-testfire.pdf` | Testfire / Altoro Mutual (testfire.net) | Identificación y explotación de XSS Reflejado en el endpoint `search.jsp`, con PoC de extracción de cookie de sesión mediante URL manipulada. Severidad High. | Burp Suite |
| `WEB/pentest-web-xvwa-xss.pdf` | XVWA | Explotación de XSS Reflejado (parámetro `item`, robo de cookies con script PHP propio) y XSS Almacenado (formulario de comentarios, control remoto del navegador con BeEF). | Burp Suite, BeEF |
| `WEB/pentest-web-xvwa-sqli.pdf` | XVWA | SQL Injection Error-based (extracción de nombre de BD vía XPATH) y Blind SQLi Boolean-based con Burp Intruder, más extracción automatizada de la tabla `users` con sqlmap. | Burp Suite, sqlmap |
| `WEB/pentest-web-dvwa.pdf` | DVWA | XSS Reflejado en el parámetro `item` (CVSS 7.1) y Command Injection / RCE mediante manipulación del campo de dirección IP. | Burp Suite |

### RED

Informes de pentest de infraestructura realizados en el curso **Pentesting en Infraestructura de Red (CBN04)**.

| Documento | Entorno | Descripción breve | Herramientas |
|---|---|---|---|
| `RED/pentesting-red-metasploitable3-lazyadmin.pdf` | Metasploitable3 + LazyAdmin (TryHackMe) | RCE en ManageEngine Desktop Central 9, SQL Injection en app Payroll, compromiso de autenticación con Pass-the-Hash, escalada de privilegios local, y DoS con MS15-034 sobre IIS. | Nmap, wfuzz, Searchsploit, Metasploit, SQLMap, Netcat, CrackStation |
| `RED/pentesting-red-infraestructura-thales.pdf` | Infraestructura de red — Servidor "Miletus" | Pentest de tipo Insider Threat/acceso físico sobre servidor Linux sin servicios de red expuestos. Explotación de configuración crítica de GRUB (sin contraseña) para editar parámetros de arranque, evadir autenticación y obtener acceso root. Extracción de flags como PoC. | GRUB, acceso físico/local |

*(Otras plataformas como HackTheBox se agregarán aquí a medida que se completen retos)*

## Herramientas Utilizadas

| Categoría | Nombre de la Herramienta | Enlace |
|---|---|---|
| **Interceptación y Manipulación HTTP** | Burp Suite | <https://portswigger.net/burp> |
| **Explotación Web** | SQLMap | <https://sqlmap.org/> |
| | BeEF | <https://beefproject.com/> |
| **Reconocimiento y Fuzzing** | Nmap | <https://nmap.org/> |
| | Gobuster | <https://github.com/OJ/gobuster> |
| | ffuf | <https://github.com/ffuf/ffuf> |
| | wfuzz | <https://github.com/xmendez/wfuzz> |
| **Explotación y Post-Explotación** | Metasploit Framework | <https://www.metasploit.com/> |
| | searchsploit (Exploit-DB) | <https://gitlab.com/exploit-database/exploitdb> |
| **Cracking de Hashes** | CrackStation | <https://crackstation.net/> |
| **OSINT / Reconocimiento** | GitHub Code Search | <https://github.com/search> |

---

*Este repositorio se actualiza continuamente con nuevos informes y writeups técnicos.*
