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
| **LazyAdmin** | [LazyAdmin-TryHackMe.pdf](TryHackMe/Easy/LazyAdmin/LazyAdmin-TryHackMe.pdf) | 🟢 Easy | Backup disclosure en SweetRice con crackeo de hash MD5, Arbitrary File Upload para reverse shell, y escalada a root vía sudo NOPASSWD sobre script Perl/shell. | Nmap, wfuzz, searchsploit, CrackStation, Netcat |
| **Grep** | [Grep-TryHackMe.pdf](TryHackMe/Easy/Grep/Grep-TryHackMe.pdf) | 🟢 Easy | OSINT sobre repo de GitHub expuesto (API key filtrada), bypass de validación de archivos para subir reverse shell PHP, RCE y extracción de credenciales de BD. | Ffuf, Netcat, PHP CLI One-liner, Burp Suite, GitHub Code Search |
| **Olympus** | [Olympus-TryHackMe.pdf](TryHackMe/Medium/Olympus/Olympus-TryHackMe.pdf) | 🟡 Medium | SQLi para extraer BD completa, cracking con John the Ripper, RCE vía upload en chat, escalada por SUID mal configurado (cputils) y backdoor oculto para acceso root. | Nmap, Ffuf, Burp Suite, John the Ripper, ssh2john, Curl, SSH, Netcat, grep, find |

### WEB

Informes de pentest en aplicaciones web realizados en el curso **Pentesting en Aplicaciones Web (CBN05)**.

| Documento | Entorno | Descripción breve | Herramientas |
|---|---|---|---|
| [pentest-web-testfire.pdf](WEB/pentest-web-testfire.pdf) | Testfire / Altoro Mutual | XSS Reflejado en `search.jsp` con PoC de robo de cookie de sesión. Severidad High. | Burp Suite |
| [pentest-web-xvwa-xss.pdf](WEB/pentest-web-xvwa-xss.pdf) | XVWA | XSS Reflejado (robo de cookies) y XSS Almacenado con control remoto del navegador vía BeEF. | Burp Suite, BeEF |
| [pentest-web-xvwa-sqli.pdf](WEB/pentest-web-xvwa-sqli.pdf) | XVWA | SQLi Error-based (XPATH) y Blind SQLi Boolean-based con Intruder, más extracción automatizada con sqlmap. | Burp Suite, sqlmap |
| [pentest-web-dvwa.pdf](WEB/pentest-web-dvwa.pdf) | DVWA | XSS Reflejado (CVSS 7.1) y Command Injection / RCE vía campo de IP. | Burp Suite |

### RED

Informes de pentest de infraestructura realizados en el curso **Pentesting en Infraestructura de Red (CBN04)**.

| Documento | Entorno | Descripción breve | Herramientas |
|---|---|---|---|
| [pentesting-red-metasploitable3-lazyadmin.pdf](RED/pentesting-red-metasploitable3-lazyadmin.pdf) | Metasploitable3 + LazyAdmin | RCE en ManageEngine Desktop Central 9, SQLi en Payroll, Pass-the-Hash, escalada local y DoS con MS15-034. | Nmap, wfuzz, Searchsploit, Metasploit, SQLMap, Netcat, CrackStation |
| [pentesting-red-infraestructura-thales.pdf](RED/pentesting-red-infraestructura-thales.pdf) | Servidor "Miletus" | Insider Threat/acceso físico: GRUB sin contraseña para evadir autenticación y obtener acceso root. | GRUB, acceso físico/local |

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
