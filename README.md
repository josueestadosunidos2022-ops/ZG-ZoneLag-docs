# ZoneLag

Server maintenance tools including dropped-item cleanup, diagnostics and existing AFK/login integration.

Herramientas de mantenimiento del servidor: limpieza de objetos tirados, diagnóstico e integración existente de AFK/login.

## Current release / Entrega actual — 2026-11-06

Minecraft **1.20.1**, Forge **47.x** (47.4.x for this release set), Java **17**. File availability follows CurseForge approval. / Disponibilidad de archivos según aprobación de CurseForge.

| Side / Lado | Version / Versión |
|---|---|
| Server / Servidor | 4.6.3 |
| Client / Cliente — retained / conservado | 2.0.3 |

**Compatibility / Compatibilidad:** Server-only update / Actualización solo servidor.

[Downloads / Descargas](https://www.curseforge.com/projects/1738049/files) · [Release guide / Guía de novedades](RELEASE-2026-11-06.md) · [Configuration / Configuración](CONFIGURATION.md)

## English — Requirements and quick start

Server: ZoneCore 2.1.0+. Keep existing compatible LoginSecurity and client files if used. This cleanup update does not require a client update.

Administrators use `/zonelag previsualizar`, `/zonelag estado`, `/zonelag limpiar`, `/zonelag posponer` and `/zonelag reload`. Preview counts loaded items only. Back up the cleanup epoch with the world.

### What changed

- Only two public cleanup notices: configurable advance warning and colored completion with removed item-unit count.
- Includes global batched cleanup from 4.6.0–4.6.2, persistent cleanup epochs and unloaded-chunk cleanup when entities load.
- Protects new drops from merging with expired drops through vanilla merging, preserves valid TOML on failed reload and applies the cleanup budget once per tick.

## Español — Requisitos e inicio

Servidor: ZoneCore 2.1.0+. Conserva LoginSecurity y clientes compatibles existentes si los usas. Esta actualización de limpieza no requiere cambiar cliente.

Administración usa `/zonelag previsualizar`, `/zonelag estado`, `/zonelag limpiar`, `/zonelag posponer` y `/zonelag reload`. La vista previa solo cuenta objetos cargados. Respalda la marca de limpieza junto al mundo.

### Novedades

- Solo dos avisos públicos: aviso previo configurable y final con colores y cantidad de unidades retiradas.
- Incluye limpieza global por lotes de 4.6.0–4.6.2, marca persistente y limpieza de chunks descargados al cargar sus entidades.
- Protege objetos nuevos de fusiones vanilla con caducados, conserva TOML válido ante recarga fallida y aplica presupuesto una vez por tick.

## Updating / Actualizar

Stop the affected instance, back up world/configuration, replace only the previous same-mod/same-side JAR and retain player data. Never install the dedicated and client JARs of one mod together. / Detén la instancia correspondiente, respalda mundo/configuración y sustituye solo el JAR del mismo mod y lado conservando datos. Nunca instales juntos los JAR dedicado y cliente del mismo mod.

## Validation scope / Alcance de verificación

4.6.3 builds/regressions and notice call sites were checked; earlier4.6.2 evidence covers protected dedicated cleanup, merges, dimensions and persistence.4.6.3 did not repeat full integration or graphical review. No production performance gain is certified.

4.6.3 revisó compilación/regresiones y emisiones;4.6.2 aporta integración dedicada protegida de limpieza, fusiones, dimensiones y persistencia.4.6.3 no repitió integración completa ni revisión gráfica. Sin mejora de rendimiento de producción certificada.

## Rights / Derechos

Original ZONE code and assets © Elgochogms; existing licenses and third-party notices remain applicable. This repository provides public documentation. / Código y recursos originales ZONE © Elgochogms; se conservan licencias y avisos de terceros. Este repositorio contiene documentación pública.
