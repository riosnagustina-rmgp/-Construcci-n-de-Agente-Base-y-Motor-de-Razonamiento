Agente de Triaje de Soporte - E-commerce

Checkpoint 1 del curso avanzado de Automatización e Inteligencia Artificial. Este flujo es la primera versión de un proyecto integrador que va a ir creciendo módulo a módulo a lo largo del curso.

Caso de uso

Agente conversacional para una tienda online de conjuntos deportivos y urbanos para mujeres, que atiende consultas de soporte de clientes (productos, pedidos, envíos, cambios, pagos y reclamos), las clasifica por categoría y prioridad, y registra los casos que necesitan intervención humana.


   
Componentes

Trigger: Chat Trigger, captura el mensaje inicial del cliente.
AI Agent: modo Tools Agent, con límite de 6 iteraciones máximas como guardrail de seguridad.
Modelo: OpenAI Chat Model (GPT-5 mini).
System Prompt: estructurado en Rol → Ámbito → Objetivo → Reglas → Restricciones → Escalamiento. Define un asistente de triaje que no inventa datos de pedidos, stock ni precios, y deriva a una persona los casos sensibles (reclamos, fraude, pedidos de reembolso).
Herramienta: Google Sheets (Append Row), conectada lateralmente al agente, con una descripción semántica extensa de cuándo debe activarse de forma autónoma.
Observabilidad: nodo de Gmail que envía un reporte con la consulta del cliente, la respuesta del agente y los pasos intermedios de su razonamiento (Execution Log).

Datos que registra

Cada caso derivado se guarda con: fecha, nombre, contacto, número de pedido, categoría, prioridad, descripción del caso y estado (Nuevo o Escalar).
