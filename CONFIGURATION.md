# ZoneLag — Configuration / Configuración (2026-11-06)

| Side / Lado | Version / Versión |
|---|---|
| Server / Servidor | 4.6.3 |
| Client / Cliente — retained / conservado | 2.0.3 |

## Cleanup / Limpieza

File: `config/ZONEMODS/zonelag/ajustes.toml`. Keep the existing `[limpieza]` section; do not duplicate it. / Conserva la sección existente sin duplicarla.

```toml
[limpieza]
max_objetos_por_tick = 128
presupuesto_microsegundos = 2000
```

Quantity range 1–4096; time range 100–10000 microseconds (2000 =2 ms). The quantity counts reviewed entries, including already-removed references. The time budget is approximate and cannot interrupt an external callback. Initial entity capture is not bounded by this removal budget. / Rango de entradas1–4096 y tiempo100–10000µs. Cuenta entradas revisadas; presupuesto aproximado, no interrumpe callbacks y no limita la captura inicial.

Existing interval, activation, warning and `zonelag.admin` permission remain. `aviso_segundos=0` disables the advance warning. Custom `limpieza.mensaje` is retained and colored; old default wording is modernized at display time without rewriting the TOML. / Conserva intervalo, activación, permiso y aviso; cero lo desactiva. Mensaje personalizado conservado y coloreado, sin reescribir TOML.

`/zonelag reload` rejects invalid replacements while keeping active configuration and pending work. Lower limits distribute removal over more ticks. `/zonelag estado` reports loaded sweep progress, limits and persistence errors. / Recarga inválida conserva configuración y trabajo; límites menores reparten trabajo. Estado informa progreso, límites y fallos.

## Persistent state / Estado persistente

Keep `<mundo>/data/zonelag-cleanup-epoch.txt`. It coordinates the cleanup mark across dimensions and restarts. It is written before removal begins; a persistence error blocks a new cleanup. Do not delete or edit it casually. / Conserva la marca: coordina dimensiones y reinicios, se guarda antes de borrar; un fallo bloquea limpieza nueva.

All loaded `ItemEntity` and subclasses are eligible, including named/modded/recent drops present when the sweep starts. Older filters for age/name/mod no longer restrict4.6.x cleanup. Inventories, chests, blocks and entities not derived from ItemEntity are outside this cleanup. / Incluye objetos cargados vanilla/mod de ItemEntity incluso con nombre; filtros antiguos no limitan4.6.x. No incluye inventarios, cofres, bloques ni entidades ajenas a ItemEntity.

Expired items in unloaded chunks are removed on entity load; chunks are not forced and their stored objects do not physically disappear from disk at the exact interval. / Lo descargado se elimina al cargar entidades; no fuerza chunks ni borra físicamente del disco al vencer el intervalo.

[Current release / Entrega actual](RELEASE-2026-11-06.md) · [README](README.md).
