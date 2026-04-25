# PegadaFit — Documentos Legais

Repositório de documentos legais do app **PegadaFit** — rede social fitness brasileira.

Este conjunto cobre os requisitos legais mínimos pra operar um app social no Brasil sob a **LGPD (Lei 13.709/2018)**, **Marco Civil da Internet (Lei 12.965/2014)**, **Código de Defesa do Consumidor (Lei 8.078/90)** e demais legislações aplicáveis.

---

## Documentos

| # | Arquivo | O que cobre |
|---|---|---|
| 01 | [Termos de Uso](01_termos_de_uso.md) | Regras gerais de uso do app, pilares (Feed, Fit, Salão, Vitrine, Perfil), responsabilidades, foro |
| 02 | [Política de Privacidade](02_politica_privacidade.md) | LGPD completa: dados coletados, bases legais, subprocessadores, direitos do titular, retenção |
| 03 | [Política de Uso Aceitável](03_uso_aceitavel.md) | Conteúdo proibido, conduta no Fit/Salão, anti-stalking, denúncias e consequências |
| 04 | [Disclaimer Médico](04_disclaimer_medico.md) | Isenção de responsabilidade por orientação fitness/saúde de outros usuários e da Vitrine |
| 05 | [Política de Cancelamento e Eliminação de Dados](05_cancelamento_e_dados.md) | Como cancelar, prazos de eliminação, dados retidos por obrigação legal |

---

## Versão atual

**Versão 1.0** — em vigor a partir de **25 de abril de 2026**.

Histórico de mudanças em [CHANGELOG.md](CHANGELOG.md).

Versionamento usado no app:

```
PRIVACY_VERSION = "1.0"
TERMS_VERSION = "1.0"
ACCEPTABLE_USE_VERSION = "1.0"
```

Ao mudar uma versão, o app deve **forçar re-aceite** do documento alterado.

---

## Controlador de dados

**Valdenor Neto** (pessoa física)
Castanhal/PA, Brasil

**E-mail / DPO:** dpo@pegadafit.com

---

## Hospedagem pública

Estes documentos devem ser publicados em URL pública pra atender:

- Exigência da Google Play Console e App Store de **Privacy Policy URL**.
- Direito do usuário de consultar a qualquer momento.
- Versionamento auditável (commits do git).

**Setup recomendado** (todo gratuito):

1. Criar repositório público **`pegadafit-legal`** no GitHub.
2. Copiar conteúdo desta pasta `legal/` pra raiz do repo.
3. Habilitar **GitHub Pages** em Settings > Pages > main branch.
4. URLs ficam em:
   ```
   https://valdenor-png.github.io/pegadafit-legal/01_termos_de_uso
   https://valdenor-png.github.io/pegadafit-legal/02_politica_privacidade
   https://valdenor-png.github.io/pegadafit-legal/03_uso_aceitavel
   https://valdenor-png.github.io/pegadafit-legal/04_disclaimer_medico
   https://valdenor-png.github.io/pegadafit-legal/05_cancelamento_e_dados
   ```
5. Quando comprar `pegadafit.app`, configurar custom domain apontando pro GitHub Pages.

Os documentos são `.md` e serão renderizados automaticamente pelo GitHub Pages com tema padrão (Cayman / minimal). Pra estilização melhor, basta adicionar `_config.yml` com tema escolhido.

---

## Atribuição (obrigatória pelas licenças CC-BY)

Os documentos 01, 02, 03 e 05 são **adaptações** de templates open-source da Basecamp (37signals LLC), licenciados sob **CC BY 4.0** ([Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/)).

Templates originais disponíveis em: https://github.com/basecamp/policies

A atribuição está incluída no rodapé de cada documento adaptado, conforme exigido pela licença.

O documento 04 (Disclaimer Médico) é **redação original** — não há atribuição pois cobre risco específico de app fitness brasileiro não previsto nos templates utilizados.

---

## Limitações deste pacote

Estes documentos foram redigidos com base em:

- Templates open-source com licença permissiva
- Conhecimento da legislação brasileira aplicável
- Arquitetura técnica específica do PegadaFit

**Não substituem revisão por advogado especialista em direito digital.** Recomenda-se revisão profissional antes de:

- Início de **monetização** (Vitrine PRO recebendo pagamento via plataforma).
- **Captação** de investimento ou rodada formal.
- Resposta a **notificação extrajudicial, intimação ou ofício da ANPD**.
- Crescimento significativo da base (ex: > 50 mil usuários ativos).

Estimativa de custo de revisão profissional: **R$ 1.500 a R$ 4.000** com advogado especialista em LGPD/direito digital. Pra MVP em piloto controlado (até 10 mil usuários em uma região, sem monetização ativa), estes documentos representam patamar razoável de proteção.

---

## Implementação no app (pendente)

Pra entrar em produção, ainda precisa:

- [x] Resumos in-app dos 5 documentos em [`src/content/legal.ts`](../src/content/legal.ts) (v2.0)
- [x] `LegalSheet.tsx` ampliado pra 5 tipos + botão "Ver versão completa" abre URL no browser
- [x] Link "Termos e Privacidade" no checkbox de **Cadastro** ([LoginScreen](../src/screens/auth/LoginScreen.tsx))
- [x] 5 links em **Configurações > Privacidade e Dados** (Termos, Privacy, Uso Aceitável, Disclaimer, Cancelamento)
- [x] Bump de idade mínima de **16 para 18** em [`CadastroScreen.tsx`](../src/screens/auth/CadastroScreen.tsx)
- [x] Tabela `consent_log` (já existia) + `registrarConsentimento` em [`services/auth.ts`](../src/services/auth.ts) — registra terms + privacy no signup
- [x] `exportarDados` (já existia) em [`services/auth.ts`](../src/services/auth.ts) — atende Direito de Portabilidade LGPD
- [ ] **Setup do repo público** `pegadafit-legal` no GitHub + GitHub Pages habilitado (URLs no `legal.ts` apontam pra `valdenor-png.github.io/pegadafit-legal/...` mas o repo precisa existir)
- [ ] Migration SQL pra inativar/notificar contas atuais com idade entre 16 e 17 (se houver — passou de 16+ pra 18+)
- [ ] Fluxo de **re-aceite forçado** quando `TERMS_VERSION` ou `PRIVACY_VERSION` no servidor for maior que a aceita pelo user (mudança 1.1 → 2.0 é material)
- [ ] Estender `consent_log` ou registrar consentimento pros novos docs (acceptable_use, medical, cancellation) — opcional, mercado considera coberto por referência nos Termos
- [ ] Preencher **Data Safety Form** no Play Console (guia em `06_data_safety_play_console.md`)

---

## Licença deste repositório

O **conteúdo dos documentos legais** desta pasta é fornecido sob **CC BY 4.0** (mesma licença dos templates originais). Você pode reutilizar como base pra outros apps mediante atribuição.

A **marca PegadaFit, logotipos e identidade visual** mencionados nos documentos não estão sob CC-BY — pertencem a Valdenor Neto.
