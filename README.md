# ZoneLag — server 4.5.1 r2 / client 2.0.3

## Update / Actualización — 2026-10-17

Selected version / Versión seleccionada: **server 4.5.1**. New file availability depends on CurseForge approval / La disponibilidad de los archivos nuevos depende de su aprobación en CurseForge.

See [changes, exact files and installation](UPDATES-2026-10-17.md) / Consulta [cambios, archivos e instalación](UPDATES-2026-10-17.md). Preserve the world and TOML files / Conserva mundo y TOML.

## Español

ZoneLag para Minecraft 1.20.1 / Forge 47.x controla limpieza de objetos, pausa de IA a distancia, tickets de chunks persistentes y expulsión por inactividad. El servidor incluye una puerta de inicio de sesión; **ZoneLag Client** presenta el libro de registro cuando se usa esa puerta. El código de autentificación y la decisión de acceso se ejecutan en el servidor.

### Instalación y compatibilidad

Descarga **ZoneLag Server 4.5.1 r2** y **ZoneLag Client 2.0.3** desde el **mismo proyecto de CurseForge**. Instala el servidor con **ZoneCore 2.1.3+**. Instala el cliente 2.0.3 en los jugadores si usas el login propio de ZoneLag. No instales el JAR servidor en clientes. Si además instalas **ZoneLoginSecurity**, este pasa a ser la autoridad de las cuentas y utiliza su propio cliente de login; ZoneLag conserva limpieza, IA, chunks y AFK. Antes de cambiar de sistema de cuentas, haz copia de seguridad y sigue la guía de migración de ZoneLoginSecurity. ZoneLag bloquea la reactivación del login antiguo si encuentra la marca de migración sin ZoneLoginSecurity.

### Comandos

| Comando | Uso |
| --- | --- |
| `/zonelag estado` | Estado de IA, chunks, AFK y login |
| `/zonelag reload` | Recarga `ajustes.toml`; activar/desactivar login y premium exige reinicio |
| `/zonelag limpiar` | Ejecuta limpieza manual |
| `/zonelag guardarcuentas` | Recuperación solo desde consola cuando ZoneLag administra las cuentas |
| `/afk` | Activa/desactiva exención de expulsión por inactividad para la sesión |

Permisos: `zonelag.admin` para administración y `zonelag.afk` para `/afk`. El permiso AFK no activa el modo automáticamente y no persiste entre conexiones. Configura `config/ZONEMODS/zonelag/ajustes.toml`; consulta [todas las claves](CONFIGURATION.md) y la [pareja de versiones](RELEASES.md). Nunca publiques `cuentas.json`, sus respaldos ni claves privadas.

## English

ZoneLag for Minecraft 1.20.1 / Forge 47.x controls dropped-item cleanup, distance-based AI pausing, persistent chunk tickets, and idle kicks. The server includes a login gate; **ZoneLag Client** displays the registration book when that gate is used. Authentication and access decisions run on the server.

### Installation and compatibility

Download **ZoneLag Server 4.5.1 r2** and **ZoneLag Client 2.0.3** from this **one CurseForge project**. The server requires **ZoneCore 2.1.3+**. Install client 2.0.3 for players when using ZoneLag's own login. Never install the server JAR on clients. With **ZoneLoginSecurity**, that mod becomes the account authority and uses its own login client; ZoneLag still handles cleanup, AI, chunks and AFK. Back up account data and follow ZoneLoginSecurity migration instructions before changing account systems. ZoneLag refuses to reactivate its old login if it finds a migration marker without ZoneLoginSecurity.

### Commands

`/zonelag estado` shows status; `/zonelag reload` reloads TOML, while login and premium activation changes require restart. `/zonelag limpiar` runs cleanup; `/zonelag guardarcuentas` is a console-only recovery command when ZoneLag owns accounts. `/afk` toggles the idle-kick exemption for the current session. Permission nodes: `zonelag.admin`, `zonelag.afk`. See [all TOML keys](CONFIGURATION.md) and [release compatibility](RELEASES.md). Never publish account files, backups or private keys.

© 2026 Elgochogms. All rights reserved for this edition. This repository contains documentation and a project avatar only; it does not contain mod source code, private obfuscation mappings or server data. Earlier versions' valid licenses remain unaffected.

