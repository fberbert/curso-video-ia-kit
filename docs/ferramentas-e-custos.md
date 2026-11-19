# Ferramentas, IAs e custos

Tudo o que é usado no curso: o que cada IA faz, os programas que a IA usa no seu computador para criar o vídeo e quanto custa cada caminho.

Preços consultados nas páginas oficiais em 17 e 19/11/2026. Eles mudam: confira antes de assinar.

## Como um vídeo nasce

Você conversa com o **omp**, o agente de IA. Ele pensa com uma IA de texto (ChatGPT, Claude, DeepSeek...) e, para fazer cada parte do vídeo, chama outras IAs e os programas instalados no seu computador:

| Etapa | Quem faz | Com o quê |
|---|---|---|
| Pesquisa | A IA de texto | Busca na internet e, com a extensão do omp no Chrome, os sites em que você já está logado |
| Roteiro | A IA de texto | - |
| Imagens (capa, ilustrações, fotos tratadas) | `gpt-image-2` (ChatGPT Plus) ou Nano Banana (Gemini) | rembg tira o fundo das fotos |
| Narração | A sua voz, a voz Kore do Gemini ou a ElevenLabs | ffmpeg limpa o ruído e nivela o volume |
| Telas animadas (números, gráficos, títulos) | A IA de texto escreve as telas como uma página web (HTML e CSS) | Chrome desenha; Node.js com Playwright grava cada quadro |
| Animações prontas (gráfico com número contando, rota em mapa 3D, produto se abrindo peça por peça) | As [skills de animação](#skills-de-animação): a IA só preenche os dados | HyperFrames, GSAP e three.js desenham; ffmpeg grava |
| Corte de silêncios e "éééé" (vídeo gravado) | auto-editor | ffmpeg |
| Legenda palavra por palavra | O tempo de cada palavra, vindo da voz de IA ou de uma transcrição do áudio | ffmpeg grava a legenda no vídeo |
| Montagem (telas, voz, música que abaixa na fala, vertical) | Um script em Python | ffmpeg |
| Avatar falante | HeyGen | ffmpeg encaixa o avatar no vídeo |
| Ajuste à mão | Você | Kdenlive |

## As IAs: quem faz o quê

### OpenAI (ChatGPT): o padrão do curso

É a IA recomendada para começar: entra no omp só com o login da sua conta, sem cartão internacional, e é a única assinatura que inclui o **`gpt-image-2`**, o gerador de imagens usado no curso.

| Plano | Preço por mês (sem impostos) | Com o omp |
|---|---|---|
| Free | R$ 0 | A OpenAI só libera o agente de programação (Codex) no aplicativo de computador, aos poucos. Não testado com o omp |
| Go | R$ 39,99 | Igual ao Free, com mais uso. Não testado com o omp |
| **Plus** | **R$ 99,90** | **Recomendado.** Funciona com o omp e inclui o `gpt-image-2` |
| Pro | R$ 999,90 | Muito mais uso; só para quem produz em volume |

### Anthropic (Claude): a preferida do instrutor para roteiro e telas

No canal Na Tabela, o roteiro e as telas são feitos com o **Claude Opus 5.5**. Na experiência do instrutor, é o modelo mais sensato nas escolhas (que dado mostrar, quando, com que destaque) e o que deixa as telas mais bonitas. No nosso teste, um modelo barato fez telas corretas, mas todas iguais e com cores mal escolhidas.

O Claude não gera imagens. Quem quiser o melhor dos dois mundos usa o Claude para pensar e o ChatGPT Plus para as imagens, pagando as duas assinaturas.

| Plano | Preço por mês |
|---|---|
| Pro | R$ 110 (ou R$ 92 por mês no plano anual, R$ 1.100 de uma vez) |
| Max | R$ 550 (5 vezes o uso do Pro) |
| Ultra | R$ 1.100 |

Todos os planos têm limite de uso, e quanto mais forte o modelo, mais rápido o limite acaba.

### Google (Gemini): voz e imagem sem assinatura

Pela mesma conta do Gmail, no Google AI Studio:

- **Voz Kore**: a voz de IA recomendada para quem não quer gravar a própria (detalhes em "Voz e avatar").
- **Nano Banana 2**: imagens por US$ 0,067 cada (1024 px), para quem não assina o ChatGPT Plus.

Para o agente pensar, o Gemini sai mais caro que DeepSeek e MiMo.

### APIs pré-pagas: o caminho econômico

Você coloca créditos em dólar, com cartão internacional, e paga só o que usar. Preço oficial em dólar por milhão de tokens. "Em cache" é o texto que o agente reenvia a cada passo e que o provedor cobra mais barato; num agente, ele é quase todo o volume.

| Provedor e modelo | Em cache | Entrada nova | Saída |
|---|---|---|---|
| DeepSeek Flash (fora do pico) | US$ 0,003 | US$ 0,15 | US$ 0,60 |
| DeepSeek V4 Pro (fora do pico) | US$ 0,022 | US$ 0,66 | US$ 1,98 |
| Xiaomi MiMo V2.6 Flash | US$ 0,0028 | US$ 0,14 | US$ 0,28 |
| Xiaomi MiMo V2.6 Pro | US$ 0,0036 | US$ 0,435 | US$ 0,87 |
| Qwen 3.7 Plus | - | US$ 0,40 | US$ 1,60 |
| Qwen 3.8 Max | - | US$ 2,00 | US$ 6,00 |
| Gemini 3.8 Flash (a partir de 01/01/2027) | US$ 0,15 | US$ 1,50 | US$ 7,50 |

- **DeepSeek:** o horário de pico é de segunda a sexta, das 22h à 1h e das 3h às 7h (horário de Brasília). No pico, o preço dobra; fim de semana é sempre fora do pico.
- **OpenRouter:** uma carteira só para centenas de modelos, com taxa de 5,5% (mínimo de US$ 0,80) na compra de créditos.
- **Na fatura do cartão** entram também o IOF de compra internacional e o câmbio do banco.

**Quanto custa na prática:** no teste de 18/11/2026, o agente com o Xiaomi MiMo V2.6 Flash criou as 9 telas animadas de um vídeo curto de 41 segundos: leu as instruções, escreveu as telas, conferiu e corrigiu. Foram 72 passos e **US$ 0,24**. O resultado veio correto, mas mais simples que o do Claude Opus. No caminho econômico, a prévia e o seu olhar de diretor contam ainda mais.

### ElevenLabs: clone da sua voz

É onde o curso demonstra o clone de voz: você grava uma amostra e a IA narra qualquer texto com a sua voz. A alternativa é o clone de voz do Gemini ("voice replication"), para quem quiser testar por conta própria.

### HeyGen: avatar falante

Cria um avatar com o seu rosto, que fala o texto do vídeo. No curso, aparece só como demonstração.

## Voz e avatar: planos

Para narrar o vídeo, o caminho mais simples é a **sua própria voz**, gravada no celular: o agente corta os silêncios e os "éééé", tira o ruído e nivela o volume. Sem custo.

| Ferramenta | Plano grátis | Plano pago |
|---|---|---|
| [Gemini TTS](https://aistudio.google.com) (voz de IA, pelo Google AI Studio) | Sim: 10 narrações por dia, no máximo 3 por minuto. A voz recomendada no curso é a **Kore** (feminina), a que soou mais natural em português do Brasil no nosso teste | US$ 0,0045 a cada 10 segundos de áudio a partir de 01/01/2027: cerca de US$ 0,03 por minuto |
| [ElevenLabs](https://elevenlabs.io/pricing) (voz de IA e clone da sua voz) | 10 mil créditos por mês (cerca de 10 minutos de fala), **sem uso comercial**: não serve para anunciar o seu negócio | Starter: US$ 6 por mês, 30 mil créditos, clone da sua voz e uso comercial |
| [HeyGen](https://www.heygen.com/pricing) (avatar falante) | 3 vídeos por mês de até 1 minuto, com marca d'água | Creator: US$ 29 por mês |

Sobre o plano grátis do Gemini:

- O limite de 10 narrações por dia vale por projeto do Google AI Studio e zera às 5h da manhã (horário de Brasília). Os limites do seu projeto aparecem em [aistudio.google.com/rate-limit](https://aistudio.google.com/rate-limit). Eles podem mudar: confira lá.
- Cada pedido de narração conta como um, mesmo que você descarte o áudio. Revise o texto antes de gerar.
- O Google usa o conteúdo enviado no plano grátis para melhorar os produtos dele.
- Para explorar depois do curso: o Gemini tem cerca de 30 vozes (no curso só testamos três).

## Os programas que a IA usa no seu computador

Todos gratuitos e disponíveis para Windows, macOS e Linux. **Instale antes da primeira aula**, seguindo os [pré-requisitos](pre-requisitos.md). Na aula, o instrutor demonstra a instalação do omp e o próprio agente confere e instala o que faltar.

| Programa | Para que serve |
|---|---|
| [omp](https://omp.sh) | O agente de IA: conversa com você, conecta as IAs e executa o trabalho. Licença MIT |
| Python | A linguagem dos scripts que organizam o vídeo: blocos do roteiro, narração, telas e montagem |
| ffmpeg | O motor de vídeo e áudio: corta, junta, deixa na vertical, legenda, limpa e nivela o som, mistura a música |
| Node.js e Playwright | Abrem as telas animadas no Chrome e gravam cada quadro, para virar vídeo |
| Google Chrome | Desenha as telas animadas. Com a extensão do omp, o agente também pesquisa nos sites em que você já está logado |
| auto-editor | Encontra e corta os silêncios de um vídeo gravado |
| rembg | Tira o fundo de fotos (pessoa ou produto recortado sobre o vídeo) |
| [Kdenlive](https://kdenlive.org/download/) | Editor de vídeo para ajuste à mão. O agente pode entregar o projeto pronto para você mexer (opcional) |
| adb (Android SDK Platform-Tools) | Manda o vídeo pronto direto para um celular Android. Opcional: no iPhone, use cabo, AirDrop ou WhatsApp Web |

### Skills de animação

Skills são roteiros de trabalho que o agente segue. O curso usa as skills de animação do Artem Novitckii (licença MIT), [adaptadas para o português](https://github.com/fberbert/claude-animation-skills): números no formato brasileiro, textos em português e instalação também no Windows. Você passa poucos dados e recebe o vídeo vertical pronto, em segundos ou em poucos minutos, no seu computador e sem custo de IA além do pedido.

| Skill | O que faz | Exemplo de pedido | Tempo de render no nosso teste |
|---|---|---|---|
| `/graph` | Uma linha que se desenha enquanto o número conta até o valor final | "Gráfico do faturamento de maio a novembro: 8,2, 9,1, 8,7, 10,4, 12,9, 15,3 e 18,8 mil reais" | 10 segundos |
| `/map-route` | Uma cidade em 3D, a rota se desenhando, o pino caindo e o cartão com tempo e distância | "Rota da loja até a casa do cliente: 4,5 km, 18 minutos" | 2 minutos |
| `/breakdown` | Um objeto se abrindo em camadas, cada peça com o nome | "O celular peça por peça, com os nomes em português" | 2 minutos |

Tempos medidos em 19/11/2026, num notebook com o processador limitado a 2 núcleos, para vídeos de 4 segundos.

O mesmo pacote traz outras animações (passos em arte de linha, estilos low-poly, Minecraft e Kurzgesagt, e dois explicadores completos com bonecos e personagens 3D) para quem quiser explorar depois do curso. Os explicadores ainda precisam do bash no Windows.

Na aula, o agente instala as skills com:

```bash
git clone https://github.com/fberbert/claude-animation-skills.git
cd claude-animation-skills
python3 install.py
```

No Windows, troque `python3` por `py`. O `install.py` coloca as skills em `~/.claude/skills`, que o omp lê.

## Fontes

- ChatGPT no Brasil: https://chatgpt.com/pt-BR/pricing/
- Codex nos planos do ChatGPT: https://learn.chatgpt.com/docs/pricing
- Claude no Brasil: https://claude.com/pricing?country=BR
- DeepSeek: https://api-docs.deepseek.com/quick_start/pricing
- Xiaomi MiMo: https://mimo.mi.com/docs/en-US/price/pay-as-you-go
- Qwen (Alibaba Cloud, região internacional): https://www.alibabacloud.com/help/en/model-studio/model-pricing
- Gemini: https://ai.google.dev/gemini-api/docs/pricing
- OpenRouter: https://openrouter.ai/docs/faq
- adb: https://developer.android.com/tools/releases/platform-tools
- Provedores aceitos pelo omp: https://omp.sh/docs/providers
