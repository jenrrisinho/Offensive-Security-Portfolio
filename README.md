# Pentesting Lab Notes

Repositorio con informes de prácticas de pentesting (red y web) realizados sobre entornos deliberadamente vulnerables, con fines de aprendizaje. Cada archivo documenta el proceso siguiendo una guía/metodología de referencia (OWASP/OSSTMM) y recoge la explotación de vulnerabilidades puntuales del entorno correspondiente.

## Aviso

Todas las pruebas se realizaron en entornos aislados y diseñados para práctica de seguridad (máquinas deliberadamente vulnerables desplegadas en laboratorio local, y la aplicación web pública de entrenamiento testfire.net). Este material es exclusivamente educativo/académico. No se debe aplicar ninguna de estas técnicas contra sistemas, redes o aplicaciones sin autorización explícita.

## Contenido

| Archivo | Entorno | Tipo | Descripción breve |
|---|---|---|---|
| `WEB/pentest-web-testfire.pdf` | Testfire / Altoro Mutual (testfire.net) | Pentesting web | Identificación y explotación de XSS Reflejado en el endpoint `search.jsp`, con PoC de extracción de cookie de sesión mediante URL manipulada. Severidad High. Herramientas: Burp Suite. |
| `WEB/pentest-web-xvwa-xss.pdf` | XVWA | Pentesting web | Explotación de XSS Reflejado (parámetro `item`, robo de cookies con script PHP propio) y XSS Almacenado (formulario de comentarios, control remoto del navegador con BeEF). Herramientas: Burp Suite, BeEF. |
| `WEB/pentest-web-xvwa-sqli.pdf` | XVWA | Pentesting web | SQL Injection Error-based (extracción de nombre de BD vía XPATH) y Blind SQLi Boolean-based con Burp Intruder, más extracción automatizada de la tabla `users` con sqlmap. Herramientas: Burp Suite, sqlmap. |
| `WEB/pentest-web-dvwa.pdf` | DVWA | Pentesting web | XSS Reflejado en el parámetro `item` (CVSS 7.1) y Command Injection / RCE mediante manipulación del campo de dirección IP. Herramientas: Burp Suite. |
| `RED/pentesting-red-metasploitable3-lazyadmin.pdf` | Metasploitable3 + LazyAdmin (TryHackMe) | Pentesting de red | RCE en ManageEngine Desktop Central 9, SQL Injection en app Payroll, compromiso de autenticación con Pass-the-Hash, escalada de privilegios local, y DoS con MS15-034 sobre IIS. Herramientas: Nmap, Metasploit, SQLMap, wfuzz. |
| `RED/pentesting-red-infraestructura-thales.pdf` | MV Thales ("Miletus") | Pentesting de red | Servidor sin servicios expuestos en red (puertos cerrados/filtrados); evaluación reorientada a seguridad física y de arranque. Explotación de GRUB sin autenticación (CWE-306) mediante inyección de `rw init=/bin/sh` en los parámetros del kernel, obteniendo shell root sin credenciales y extrayendo las flags de usuario y root. |

## Herramientas utilizadas (según el ejercicio)

- **Reconocimiento / red:** Nmap
- **Explotación:** Metasploit Framework, exploits manuales, manipulación de parámetros de kernel/GRUB (acceso físico)
- **Web:** Burp Suite (Repeater/Intruder), SQLMap, wfuzz, BeEF, payloads manuales

## Estructura

```
pentesting-portfolio/
├── WEB/
│   ├── pentest-web-testfire.pdf
│   ├── pentest-web-xvwa-xss.pdf
│   ├── pentest-web-xvwa-sqli.pdf
│   └── pentest-web-dvwa.pdf
└── RED/
    ├── pentesting-red-metasploitable3-lazyadmin.pdf
    └── pentesting-red-infraestructura-thales.pdf
```
