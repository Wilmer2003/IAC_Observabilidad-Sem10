# IAC_Observabilidad-Sem10
Aprenderemos sobre el monitoreo de herramientas disponibles para desplegar una app web


1. ¿Por qué necesitamos Loki además de Prometheus si ya tenemos /metrics?
Prometheus solo guarda números en el tiempo (métricas). Loki guarda texto (logs). Con /metrics sabes que hubo 5 errores, pero con Loki sabes exactamente qué error fue, cuándo y en qué servicio.

2. ¿Qué ventaja aporta que las fuentes de datos estén aprovisionadas como código?
Que son reproducibles — cualquier persona que clone el repo obtiene exactamente la misma configuración sin hacer clic a mano. Si el servidor se cae, se levanta igual con un solo comando.

3. ¿Por qué CPU contenedor y CPU host pueden mostrar valores distintos? ¿Cuál usarías para alertar?
El host mide toda la máquina incluyendo el sistema operativo y todos los procesos. El contenedor mide solo esa app. Para alertar sobre una aplicación concreta usarías el panel de contenedor porque es más preciso.

4. ¿Qué diferencia hay entre evaluation interval y pending period?
El evaluation interval es cada cuánto Grafana revisa la métrica (cada 10s). El pending period es cuánto tiempo debe mantenerse la condición antes de disparar la alarma (30s). El pending period evita falsas alarmas por picos cortos.
