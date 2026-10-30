# Práctica Agentes RAG con n8n

Asistente inteligente de soporte interno con RAG (n8n + Ollama + Pinecone + Google Sheets).

## Workflows

| Archivo | Descripción | Autor |
|---|---|---|
| `workflows/WF1_Ingesta_RAG.json` | Ingesta: Drive → PDF → catálogo (Sheets) → borrado de versión anterior → troceado por secciones → Pinecone (`soporte-vigente`) | Alfonso |
| `workflows/WF3_Agente_soporte.json` | Agente: Chat → AI Agent (qwen3:8b) + memoria + RAG (Pinecone) + consulta de solicitudes (Sheets) | Alfonso |
| `workflows/WF2_...json` | Solicitudes / incidencias | Compañero |
| `workflows/WF4_...json` | Error Workflow + aprobación humana | Compañero |

## Importar
En n8n: *Workflows → Import from File*. Los JSON se exportan **sin credenciales**: al importarlos hay que asignar en cada nodo las credenciales propias (Ollama, Pinecone, Google Drive/Sheets).

## Herramientas (gratuitas)
n8n (Docker), Ollama (`qwen3:8b`, `nomic-embed-text:v1.5`), Pinecone (plan gratuito, índice 768 dim, coseno), Google Drive y Google Sheets.
