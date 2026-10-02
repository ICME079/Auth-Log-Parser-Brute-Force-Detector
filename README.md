# Auth-Log-Parser-Brute-Force-Detector
Herramienta de análisis de registros de autenticación en Python diseñada para auditar eventos en servidores Linux (`/var/log/auth.log`) y detectar de forma automática ataques de fuerza bruta dirigidos al servicio SSH.

Este repositorio contiene la lógica para procesar volúmenes densos de texto plano provenientes de bitácoras del sistema y transformarlos en métricas de seguridad accionables:

1. **Motor de Parsing (`analyzer.py`):**
   - Extrae marcas de tiempo, direcciones IP de origen, estados de autenticación (`Accepted` / `Failed`) y nombres de usuario evaluados mediante expresiones regulares estructuradas.
2. **Detección de Patrones Anómalos:**
   - Correlaciona intentos fallidos consecutivos contra umbrales configurables para identificar hosts atacantes.
   - Identifica técnicas de enumeración de cuentas comunes (`root`, `admin`, `guest`).
3. **Módulo de Reportes:**
   - Genera resúmenes ejecutivos en consola con el top de atacantes y porcentajes de afectación.
   - Permite la exportación de resultados a formato JSON para integrarse con tableros o herramientas de visualización.
4. **Datos de Muestra (`sample_logs/`):**
   - Incluye fragmentos anonimizados de bitácoras reales con patrones de ataque simulados para realizar pruebas inmediatas sin comprometer datos sensibles.
