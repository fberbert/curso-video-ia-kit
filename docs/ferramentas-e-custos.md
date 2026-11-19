# Ferramentas e custos

Preços consultados nas páginas oficiais em 17/11/2026. Eles mudam: confira antes de assinar.

## O que instalar (gratuito)

| Ferramenta | Para quê |
|---|---|
| [omp](https://omp.sh) | O agente de IA: conecta as IAs e executa o trabalho. Licença MIT. Windows, macOS e Linux |
| ffmpeg | O motor de vídeo: corta, junta, legenda, mistura o som |
| Python | Os scripts da esteira de vídeo |
| Google Chrome | Desenha e captura as telas animadas; com a extensão do omp, pesquisa nos sites em que você já está logado |
| [Kdenlive](https://kdenlive.org/download/) | Editor de vídeo para ajuste manual (opcional) |

O passo a passo de instalação para cada sistema entra neste repositório antes do curso.

## A IA por trás do agente

O omp é o volante; a IA é o motor. Dá para trocar o motor sem trocar o jeito de trabalhar. São dois caminhos:

### Padrão: ChatGPT Plus

- **R$ 99,90 por mês** (sem impostos). Pode cancelar depois do curso.
- Entra no omp só com o login da sua conta, sem cartão internacional nem recarga em dólar.
- Inclui o `gpt-image-2`, que gera as imagens e capas.

### Econômico: API pré-paga

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
- **Imagens sem assinatura:** o Gemini 3.1 Flash Image (Nano Banana 2) cobra US$ 0,067 por imagem de 1024 px.
- **Na fatura do cartão** entram também o IOF de compra internacional e o câmbio do banco.

### Quanto custa na prática

Teste de 18/11/2026: o agente, com o Xiaomi MiMo V2.6 Flash, criou as 9 telas animadas de um vídeo curto de 41 segundos. Ele leu as instruções, escreveu as telas, conferiu e corrigiu. Foram 72 passos e **US$ 0,24**. A narração já estava gravada.

O resultado veio correto, mas mais simples que o feito com os modelos mais caros: telas todas do mesmo tipo e cores menos bem escolhidas. No caminho econômico, a prévia e o seu olhar de diretor contam ainda mais.

## Voz e avatar (opcionais)

Para narrar o vídeo, o caminho mais simples é a **sua própria voz**, gravada no celular: o agente corta os silêncios e os "éééé", tira o ruído e nivela o volume. Sem custo.

| Ferramenta | Plano grátis | Plano pago |
|---|---|---|
| [Gemini TTS](https://aistudio.google.com) (voz de IA, pelo Google AI Studio) | Sim, com limite diário. A voz recomendada no curso é a **Kore** (feminina), a que soou mais natural em português do Brasil no nosso teste | US$ 0,0045 a cada 10 segundos de áudio a partir de 01/01/2027: cerca de US$ 0,03 por minuto |
| [ElevenLabs](https://elevenlabs.io/pricing) (voz de IA e clone da sua voz) | 10 mil créditos por mês (cerca de 10 minutos de fala), **sem uso comercial**: não serve para anunciar o seu negócio | Starter: US$ 6 por mês, 30 mil créditos, clone da sua voz e uso comercial |
| [HeyGen](https://www.heygen.com/pricing) (avatar falante) | 3 vídeos por mês de até 1 minuto, com marca d'água | Creator: US$ 29 por mês |

No plano grátis do Gemini, o Google usa o conteúdo enviado para melhorar os produtos dele. O avatar aparece no curso só como demonstração.

## Fontes

- ChatGPT no Brasil: https://chatgpt.com/pt-BR/pricing/
- DeepSeek: https://api-docs.deepseek.com/quick_start/pricing
- Xiaomi MiMo: https://mimo.mi.com/docs/en-US/price/pay-as-you-go
- Qwen (Alibaba Cloud, região internacional): https://www.alibabacloud.com/help/en/model-studio/model-pricing
- Gemini: https://ai.google.dev/gemini-api/docs/pricing
- OpenRouter: https://openrouter.ai/docs/faq
- Provedores aceitos pelo omp: https://omp.sh/docs/providers
