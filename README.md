# Assinatura de e-mail — the map · Danilo Colombo

Arquivos para montar a assinatura de e-mail da the map.

## Arquivos

| Arquivo | O que é |
|---|---|
| `signature-full.png` | **Card completo** (painel + quadrado verde), 800×294 em @2x. É o arquivo para o Gmail. |
| `signature-left.png` | Só o painel de informação (507×294 @2x). Para a versão HTML de 2 blocos. |
| `signature-video.gif` | **Bloco animado** (293×294, ~1,1 MB): o vídeo oficial da marca — homem lendo o mapa (P&B) fechando no logo "the map." em verde. Para a versão HTML. |
| `signature-right-green.png` | Bloco verde estático (293×294 @2x). Alternativa sem animação. |
| `signature-email.html` | Versão em HTML (n8n / clientes que aceitam HTML). **Não serve para o Gmail.** |
| `signature-email-preview.html` | Abre no navegador para conferir o resultado localmente. |
| `assinatura the map.fig` | Arquivo-fonte do Figma. |

---

## ✅ Como colocar no Gmail (jeito que funciona)

O editor de assinatura do Gmail **não aceita colar código HTML** e **ignora
mapas de imagem** (aquele truque de deixar só um pedaço clicável). Por isso a
tentativa anterior não funcionou. O caminho confiável é usar **uma única imagem**.

1. Abra o Gmail no computador (navegador).
2. Clique na **engrenagem** (canto superior direito) → **Ver todas as configurações**.
3. Na aba **Geral**, desça até **Assinatura**.
4. Clique em **Criar** (ou edite a assinatura existente) e dê um nome.
5. Na barrinha de formatação da caixa de assinatura, clique no ícone de
   **Inserir imagem** (🏞️).
6. Escolha a aba **Fazer upload** e envie o arquivo **`signature-full.png`**.
   > A aba "Fazer upload" hospeda a imagem no próprio Google — você **não precisa**
   > de repositório público nem de link nenhum.
7. A imagem aparece grande. Clique nela uma vez para selecioná-la e, no menu
   que surge, escolha o **tamanho pequeno/médio** se quiser reduzir (a imagem é
   @2x, então fica nítida mesmo menor).
8. **(opcional, para deixar clicável)** com a imagem selecionada, clique no
   ícone de **link** (🔗) e cole `https://themap.ag` (ou
   `https://wa.me/5511983261097` se preferir levar pro WhatsApp).
9. Em **Padrões de assinatura**, escolha essa assinatura para
   **NOVOS E-MAILS** e para **RESPOSTAS/ENCAMINHAMENTOS**.
10. Role até o final da página e clique em **Salvar alterações**.

Pronto — mande um e-mail de teste para você mesmo para conferir.

### Observações
- **Telefone / WhatsApp clicável:** o número aparece na imagem e é legível, mas
  uma imagem só aceita **um** link. Se quiser vários links clicáveis (site,
  WhatsApp, e-mail), a saída é escrever uma linha de texto com links **abaixo**
  da imagem, direto na caixa de assinatura. Posso montar essa linha se quiser.
- **App do celular:** o app do Gmail no celular costuma usar uma assinatura de
  texto separada. Configure pelo navegador do computador; a assinatura com
  imagem vale para os e-mails enviados dali.

---

## Versão em HTML (n8n e clientes que aceitam HTML)

Só use se for enviar por **n8n** ou outro cliente que aceite HTML de verdade
(o Gmail não aceita — veja acima).

O repositório é **público**, então as imagens já são servidas pelo jsDelivr.
É só copiar o bloco `<table>…</table>` do `signature-email.html` e colar no HTML
da assinatura do n8n — as URLs já apontam para um endereço público.

As URLs estão **fixadas no commit** (imutáveis), então funcionam mesmo antes de
dar merge na `main`:
`https://cdn.jsdelivr.net/gh/danilo-the-map/assinatura@9c0c020…/signature-left.png`
`https://cdn.jsdelivr.net/gh/danilo-the-map/assinatura@9c0c020…/signature-video.gif`

(Opcional: depois do merge na `main`, dá para trocar `@9c0c020…` por `@main`.)

Nessa versão: clicar no **painel** leva ao WhatsApp e clicar no **bloco verde
animado** leva a `themap.ag`.

---

## Notas técnicas

- O `signature-video.gif` é o **vídeo oficial da marca** (1000×1000, quadrado —
  encaixa no bloco sem cortar as laterais): homem lendo o mapa em P&B dentro da
  moldura verde, fechando no logo "the map." em verde. Convertido a 9 fps com
  paleta reduzida (~1,1 MB) para rodar bem em e-mail, mantendo a duração total.
- Existe também `signature-right-green.png` (bloco verde estático) caso queira
  uma versão sem animação.
- As imagens foram renderizadas a partir do design do Figma em **@2x** (o dobro
  da resolução) para ficarem nítidas em telas retina.
- A fonte **Hubot Sans** está **embutida no HTML de renderização em base64** —
  não depende de CDN. (Antes o texto caía no fallback Arial porque o CDN da
  fonte era bloqueado na hora de gerar a imagem.)
- Elementos conferidos contra o thumbnail do próprio `.fig` para bater com o
  Figma: ícone do WhatsApp dentro da pílula (asset extraído do `.fig`), ícone
  "union" (círculo + linha horizontal) e "strategy studio / map method // 2026"
  centralizado verticalmente nesse ícone.
