# ZoneLag 4.3.1 — TOML / Configuración

Generated server file / Archivo generado del servidor: `config/ZONEMODS/zonelag/ajustes.toml`. `/zonelag reload` validates a whole snapshot; changing `login.activo` or `login.premium_automatico` requires restart. / La recarga valida el archivo completo; cambiar activación de login o premium requiere reinicio. Back up before editing / Haz copia antes de editar.

| Group / Grupo | Keys and defaults / Claves y valores iniciales | Effect / Efecto |
| --- | --- | --- |
| `limpieza` | `activa=true`, `intervalo_segundos=300`, `aviso_segundos=30`, `mensaje=...` | Dropped-item cleanup and warning / Limpieza y aviso; interval must exceed warning. |
| `limpieza` | `objetos_vanilla=true`, `objetos_mods=true`, `objetos_con_nombre=true`, `edad_minima_segundos=0`, `mods_excluidos=[]` | Choose affected ground items; does not delete inventories or blocks / Filtra objetos en el suelo. |
| `ia` | `activa=true`, `distancia_bloques=10`, `afectar_vanilla=true`, `afectar_mods=true`, `mods_excluidos=[]` | Pause distant mobs without saving permanent `NoAI` / Pausa IA a distancia. |
| `chunks` | `activo=true`, `distancia_bloques=30`, `suspender_forzados_vanilla=true`, `suspender_cargadores_forge=true`, `suspender_otros_persistentes=false`, `tickets_excluidos=[]` | Suspends selected persistent tickets outside range; temporary tickets remain active / Suspende cargadores persistentes seleccionados. |
| `afk` | `activo=true`, `tiempo_segundos=600`, `afectar_operadores=true`, `afectar_espectadores=true` | Idle kick policy / Expulsión por inactividad. `/afk` requires `zonelag.afk` and is session-only. |
| `login` | `activo=true`, `premium_automatico=true`, `plazo_segundos=120`, `intentos=5`, `longitud_minima=8` | ZoneLag's own login when ZoneLoginSecurity is absent / Login propio si falta ZoneLoginSecurity. |

Limits from source / Límites del código: `limpieza.intervalo_segundos` 2–86400; `aviso_segundos` 0–3600 and less than interval; `edad_minima_segundos` 0–86400; `ia.distancia_bloques` 1–256; `chunks.distancia_bloques` 1–1024; `afk.tiempo_segundos` 5–86400; `login.plazo_segundos` 15–600; `login.intentos` 1–20; `login.longitud_minima` 8–32. Exclusion lists accept up to 256 identifiers. / Las listas de exclusión admiten hasta 256 identificadores.

`limpieza.mensaje` may use `{segundos}`. The standalone login stores salted password hashes in `config/ZONEMODS/zonelag/cuentas.json` with a `.bak` backup; those are **private player data**, not configuration to share. When ZoneLoginSecurity owns accounts, follow its SQLite/TLS migration guide instead. / `cuentas.json` y su respaldo son datos privados; no los compartas. El login de ZoneLoginSecurity usa su propia migración.

