# ZoneLag — compatibility / Compatibilidad

## Beta pair / Pareja Beta — server 4.3.1 + client 2.0.3

One CurseForge project `1738049`, two side-specific files. Minecraft 1.20.1, Forge 47.4.x, Java 17. ZoneLag Server 4.3.1 requires ZoneCore 2.1.3+ on the server. ZoneLag Client 2.0.3 is the matching UI for the built-in login protocol 2; it requires Forge/Minecraft on the client. With ZoneLoginSecurity 1.1.2, account authority moves to that mod, so follow its separate client instructions. / Un proyecto con dos archivos: servidor 4.3.1 y cliente 2.0.3. El cliente se usa para el login propio; con ZoneLoginSecurity se usa el cliente de ese sistema.

| File / Archivo | SHA-256 |
| --- | --- |
| `zonelag-4.3.1-protected.jar` | `0D5FF2A25C4AC57815E1631F9096C200BE1660A0EFF7CB37AF24C0683665A573` |
| `zonelag-client-2.0.3-protected.jar` | `68D68A353F50F4D17080C5FEF9F132FC1D51D85EFD8683198F2C1A9CE4D8B8A4` |

Both modules built. Five password/account regression checks passed on server source; final protected server JAR started, answered `/zonelag estado`, and stopped cleanly on isolated Forge 47.4.10 with protected Core 2.1.3. An earlier protected candidate that differed only in the client-version error text also answered `/zonelag reload` and started with ZoneLoginSecurity 1.1.2 present (unprotected local build). The protected JAR keeps the exact coremod hook names and `Auth.denied` API used by ZoneEconomy; private internal code is obfuscated. These checks do not prove a successful real player login, premium authentication, graphical client, full modpack, or production hosting. / Pasaron compilaciones, cinco regresiones y arranques aislados, también con ZoneLoginSecurity presente; faltan login real, cliente gráfico, modpack y hosting.

The coremod JavaScript and required hook signatures remain inspectable inside a JAR. Java bytecode cannot be made impossible to decompile; the server remains the authority for access decisions. / El JavaScript del coremod y las firmas obligatorias son visibles. La ofuscación dificulta lectura, pero no puede impedir descompilar por completo.

