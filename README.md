# Assinatura de e-mail — the map · Danilo Colombo

Arquivos para montar a assinatura de e-mail da the map.

## Arquivos

| Arquivo | O que é |
|---|---|
| `signature-full.png` | **Card completo** (painel + quadrado verde), 800×294 em @2x. É o arquivo para o Gmail. |
| `signature-left.png` | Só o painel de informação (507×294 @2x). Para a versão HTML de 2 blocos. |
| `signature-right-green.png` | Só o quadrado verde (293×294 @2x). Para a versão HTML de 2 blocos. |
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

1. Deixe o repositório `danilo-the-map/assinatura` **público** e os PNGs na
   branch `main` (imagens de e-mail e o jsDelivr não carregam de repo privado).
2. Copie todo o bloco `<table>…</table>` do arquivo `signature-email.html`.
3. As imagens são servidas por
   `https://cdn.jsdelivr.net/gh/danilo-the-map/assinatura@main/...`.

Nessa versão: clicar no **painel** leva ao WhatsApp e clicar no **quadrado
verde** leva a `themap.ag`.

---

## Notas técnicas

- O `signature-video.gif` que estava no repositório era um export quebrado
  (100 quadros praticamente pretos, em escala de cinza) — não era o quadrado
  verde da marca. Por isso não foi usado. O lado direito agora é o quadrado
  verde sólido do design do Figma. Se você tiver o vídeo original (.mp4), dá
  para gerar um GIF animado correto e trocar.
- As imagens foram renderizadas a partir do design do Figma em **@2x** (o dobro
  da resolução) para ficarem nítidas em telas retina. A fonte é **Hubot Sans**.
- O ícone de localização ao lado de "strategy studio" foi recriado. Se houver um
  logo/ícone oficial da the map, me envie que eu troco pelo original.
