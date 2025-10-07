# System Prompt: Arquiteto de Aprendizado Estruturado

## 🎯 Objetivo

Este repositório contém um **system prompt otimizado** que transforma qualquer pergunta sobre aprendizado em um **roteiro estruturado e acionável**.

A grande vantagem: quebra desafios de **escopo aberto** (exploração livre) em **tarefas de escopo fechado** (ações concretas e mensuráveis), facilitando o foco e progresso contínuo.

## 💡 Por que usar?

Resolve o problema de respostas vagas de IA ao:
- ✅ **Estruturar qualquer tópico** em fases progressivas
- ✅ **Separar conceitos (teoria)** de tarefas (prática)**
- ✅ **Fornecer tarefas específicas** com critérios de sucesso claros
- ✅ **Incluir recursos verificados** (docs oficiais, repos, tutoriais)
- ✅ **Instruir a IA a pesquisar informações atualizadas** na web

## 📄 Arquivo Principal

### `system_prompt.md`
**Prompt completo e único em português** com:
- Instruções para pesquisa web automática
- Estrutura de 4-5 fases progressivas
- Regras rígidas para tarefas de escopo fechado
- Exemplos multi-domínio (tech, criativo, negócios)
- Checklist de qualidade integrada

## 🚀 Como Usar

### Com OpenAI API
```python
import openai

with open('system_prompt.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "Como aprender Rust?"}
    ]
)

print(response.choices[0].message.content)
```

### Com Claude (Anthropic)
```python
import anthropic

with open('system_prompt.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

client = anthropic.Anthropic(api_key="sua-chave")
response = client.messages.create(
    model="claude-3-sonnet-20240229",
    system=system_prompt,
    messages=[{"role": "user", "content": "Como criar apps mobile?"}]
)

print(response.content[0].text)
```

### Com Modelos Locais (Ollama, LM Studio)
```python
# Exemplo com Ollama
import requests

with open('system_prompt.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

response = requests.post('http://localhost:11434/api/chat', json={
    "model": "mistral",
    "messages": [
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "Como aprender Docker?"}
    ]
})
```

## 📋 Estrutura de Saída Esperada

```markdown
[Introdução contextual 2-3 frases]

🧭 Fase 1 – Fundamentos (escopo aberto)
Objetivo: [Meta clara]

Conceitos a entender:
• [Conceito]: [Explicação prática]
• [...]

Recursos para estudo:
• [Documentação oficial]
• [Repositório GitHub]
• [Tutorial/curso]
• [Comunidade]

✅ Tarefas de escopo fechado (fase 1)
□ Instalar [ferramenta] usando [comando]
□ Criar [artefato] que [faz X]
□ Testar com [método] verificando [resultado]
□ Documentar em [arquivo]

⚙️ Fase 2 – Prática (escopo aberto)
[...]

🎮 Fase 3 – Integração (escopo aberto)
[...]

🧩 Fase 4 – Aprofundamento (escopo aberto)
[...]

🧠 Fase 5 – Maestria (escopo aberto)
[...]

---
💡 **Próximos Passos**
[Ofertas de detalhamento]
```

## 🎨 Características Principais

### Fases Progressivas
1. **🧭 Fundamentos** - Setup e conceitos base
2. **⚙️ Prática** - Primeira aplicação funcional
3. **🎮 Integração** - Aplicação no mundo real
4. **🧩 Aprofundamento** - Padrões avançados
5. **🧠 Maestria** - Contribuição e ensino

### Tarefas de Qualidade
- ✅ Verbos de ação (Instalar, Criar, Testar)
- ✅ Artefatos específicos (arquivos, comandos)
- ✅ Critérios de sucesso claros
- ✅ Estimativas de tempo (30min-2h)
- ❌ NUNCA tarefas vagas ("Aprenda sobre...")

### Recursos Priorizados
1. Documentação oficial
2. Repositórios GitHub oficiais
3. Tutoriais de plataformas reconhecidas
4. Comunidades ativas
5. Blogs técnicos recentes (<1 ano)

## 📊 Exemplos Práticos

### Entrada
```
"Como criar APIs REST em Python?"
```

### Saída (resumida)
```
Fase 1: HTTP, REST, setup FastAPI
Tarefas:
□ pip install fastapi uvicorn
□ Criar main.py com endpoint GET /health
□ Testar: curl localhost:8000/health
□ Documentar estrutura em README.md

Fase 2: CRUD completo com banco de dados
[...]
```

## 🔧 Personalização

Para adaptar o prompt:

1. **Ajustar complexidade**: Modifique número de fases (linha que define 4-5 fases)
2. **Adicionar domínios**: Expanda seção "Exemplos de Aplicação por Domínio"
3. **Mudar idioma**: Substitua labels portuguesas mantendo estrutura
4. **Ajustar estimativas**: Altere seção "Estimativas de Tempo"

## ⚡ Dicas de Uso

### Para Iniciantes
- Use com tópicos amplos: "Aprender programação"
- A IA estruturará do zero

### Para Intermediários
- Seja específico: "FastAPI com PostgreSQL"
- Fases focarão no que ainda não sabe

### Para Avançados
- Pergunte sobre tópicos nicho: "Otimizar queries N+1"
- Fases serão mais técnicas

### Para Projetos
- Descreva o projeto: "Chat real-time com WebSocket"
- A IA estruturará as tecnologias necessárias

## 📈 Casos de Uso

✅ **Aprender nova tecnologia** (linguagem, framework, tool)
✅ **Começar novo hobby** (música, 3D, design)
✅ **Iniciar negócio** (startup, freelance, produto)
✅ **Dominar conceito** (algoritmos, padrões, arquitetura)
✅ **Executar projeto** (app, site, automação)

## 🎓 Filosofia

Este prompt se baseia no princípio de que **aprendizado efetivo = tarefas concretas**.

Ao invés de:
- ❌ "Estude React"
- ❌ "Familiarize-se com hooks"

Você recebe:
- ✅ "Crie componente Counter.jsx usando useState"
- ✅ "Implemente useEffect para fetch de API"

**Resultado**: Progresso mensurável e foco mantido.

## 📦 O que você obtém

Ao usar este prompt, cada resposta garante:

1. **Clareza total** - Caminho definido do início ao fim
2. **Ação imediata** - Tarefas para começar hoje
3. **Recursos verificados** - Links e referências confiáveis
4. **Critérios de progresso** - Como saber que avançou
5. **Foco mantido** - Sem perder tempo decidindo o que fazer

## 🔗 Recursos Relacionados

- [OpenAI Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic Prompt Library](https://docs.anthropic.com/claude/prompt-library)
- [LangChain Prompt Templates](https://python.langchain.com/docs/modules/model_io/prompts/)

## 📄 Licença

MIT - Use livremente em seus projetos pessoais ou comerciais.

---

**Desenvolvido para facilitar aprendizado através de estrutura e ação.**
