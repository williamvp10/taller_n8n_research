# Agente de Investigación Automatizado con n8n

Este proyecto contiene el instructivo para crear un agente conversacional que realiza investigación web, organiza hallazgos y genera un informe en PDF con fuentes citadas, usando n8n y herramientas externas. 

## Contenidos
- Guía detallada del taller: `./Instructivo-Taller-n8n.md`
- Workflows listos para importar:
  - `Research Agent taller n8n.json` (Agente Principal)
  - `Sub-Workflow research.json` (Subworkflow de investigación)
- Imágenes de apoyo: `./imagenes/`

## Arquitectura
- Chat → AI Agent → Sub-Workflow → HTML → PDF.

## Requisitos
- Cuenta en n8n Cloud: https://app.n8n.cloud/register
- API Key de Tavily: https://tavily.com/ (Docs: https://docs.tavily.com/)
- API Key de Gemini (Google AI): https://ai.google.dev/aistudio (Docs: https://ai.google.dev/gemini-api/docs)
- API Key de PDF.co: https://pdf.co/
- Nodos de comunidad en n8n:
  - `@tavily/n8n-nodes-tavily`
  - `@pdfco/n8n-nodes-pdfco`

## Configuración en n8n
- Instalar nodos de comunidad: Settings → Community Nodes → Install → agrega `@tavily/n8n-nodes-tavily` y `@pdfco/n8n-nodes-pdfco`.
- Crear credenciales:
  - `Google Gemini (PaLM)` → pega tu API key de Gemini. Modelo recomendado: `models/gemini-2.5-flash`.
  - `Tavily API` → pega tu API key.
  - `PDF.co` → pega tu API key.

## Importar Workflows
- En n8n, ve a Workflows → `Import from file` e importa:
  - `Research Agent taller n8n.json`
  - `Sub-Workflow research.json`
- Abre el workflow del agente principal y en el nodo `Call n8n Workflow Tool` selecciona el subworkflow `Sub-Workflow research`.
- Activa ambos workflows.

## Uso rápido
- Abre el chat del Agente Principal.
- Escribe tu solicitud de investigación; el agente hará preguntas de aclaración si es necesario.
- Recibirás resumen ejecutivo, fuentes y un `research_url` con el PDF del informe.

## Estructura del repositorio
- `Instructivo-Taller-n8n.md`: guía paso a paso para construir y configurar los workflows.
- `Research Agent taller n8n.json`: definición del agente principal.
- `Sub-Workflow research.json`: definición del subworkflow de investigación.
- `imagenes/`: recursos visuales (capturas/diagramas).

## Recursos
- n8n Cloud: https://app.n8n.cloud/register
- Tavily: https://tavily.com/ | Docs: https://docs.tavily.com/
- Google Gemini API: https://ai.google.dev/aistudio | Docs: https://ai.google.dev/gemini-api/docs
- PDF.co: https://pdf.co/

## Notas
- No compartas tus API keys en el repositorio público.
- Para pasos detallados, sigue `./Instructivo-Taller-n8n.md`.