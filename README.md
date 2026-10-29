<div align="center">

# 📡 LENDA-435

**Monopolo Coaxial Tático UHF · Calibrado em Bancada**

[![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-Online-10b981?style=for-the-badge&logo=github)](https://lenda-435.github.io/)
[![Faixa](https://img.shields.io/badge/Faixa-430_a_440_MHz-ff4d00?style=for-the-badge)](https://lenda-435.github.io/)
[![ROE / SWR](https://img.shields.io/badge/ROE-1.37_@_436_MHz-38bdf8?style=for-the-badge)](https://lenda-435.github.io/)
[![Impedância](https://img.shields.io/badge/Impedância-50_Ω-f59e0b?style=for-the-badge)](https://lenda-435.github.io/)
[![Conector](https://img.shields.io/badge/Conector-SMA_Fêmea-64748b?style=for-the-badge)](https://lenda-435.github.io/)

<br>

<img src="/lenda-435/img/lenda435.jpg" alt="Antena LENDA-435 em ambiente de campo" width="800" style="border-radius: 12px;">

<br><br>

> *Antena portátil de alto rendimento para rádio comunicador HT (Baofeng UV-5R, UV-21 Pro, Quansheng e compatíveis), construída a partir de cabo coaxial RG-213 de especificação militar com alma de 7 vias e equalizada individualmente via analisador vetorial de rede (NanoVNA).*

</div>

---

## 📋 Sumário

- [Visão Geral e Proposta](#-visão-geral-e-proposta)
- [Especificações Técnicas](#-especificações-técnicas)
- [Engenharia e Arquitetura Construtiva](#-engenharia-e-arquitetura-construtiva)
- [Validação em Bancada (NanoVNA-F / VNAmate)](#-validação-em-bancada-nanovna-f--vnamate)
- [Lista de Materiais (BOM)](#-lista-de-materiais-bom)
- [Dimensões de Corte e Montagem](#-dimensões-de-corte-e-montagem)
- [Política de Garantia](#-política-de-garantia)
- [Aviso Regulatório (Anatel)](#-aviso-regulatório-anatel)
- [Site Oficial e Contato](#-site-oficial-e-contato)

---

## 🎯 Visão Geral e Proposta

A maioria das antenas comerciais de baixo custo para transceptores portáteis (HT) apresenta três vulnerabilidades críticas em operações severas (off-road, UTVs, trilhas, expedições e equipes de apoio):

1. **Fragilidade Mecânica:** Antenas dobráveis ("táticas de fita") ou cabos com alma de cobre sólido quebram internamente por fadiga de material após flexões repetidas e atrito com galhos.
2. **Perdas por Descasamento (ROE Elevada):** Antenas genéricas raramente são aferidas uma a uma, operando com taxa de onda estacionária elevada que drena a bateria e dissipa RF em forma de calor no estágio final do rádio.
3. **Efeito de Mão e Radiação Ineficiente:** Antenas de fábrica (*rubber duck*) possuem ganho negativo e sofrem grande variação de impedância ao toque do operador.

A **LENDA-435** soluciona esses problemas adotando a arquitetura de **monopolo coaxial com luva de desacoplamento** em cabo RG-213, garantindo integridade mecânica de 7 vias multifilares, blindagem com termorretrátil vulcanizante 3:1 e casamento de impedância cravado na faixa útil de UHF (430 a 440 MHz).

---

## ⚙️ Especificações Técnicas

| Parâmetro | Especificação Nominal / Medida |
| :--- | :--- |
| **Tipo de Antena** | Monopolo Coaxial Tático UHF |
| **Faixa Operacional Calibrada** | 430.000 MHz a 440.000 MHz |
| **Frequência de Ressonância Central** | 435.000 MHz |
| **ROE / SWR Típico** | **1.37** em 435 MHz (1.36 a 1.46 em toda a faixa 430–440 MHz) |
| **Impedância Característica ($Z$)** | $50\ \Omega$ nominal ($44.3\ \Omega + j13.6\ \Omega$ no vale) |
| **Perda de Retorno (Return Loss)** | **15.9 dB** a 16.3 dB |
| **Perda por Descasamento (Mismatch Loss)** | **0,1 dB** (transferência de ~98% da potência de RF) |
| **Comprimento Físico Total** | $\approx 265\text{ mm}$ a $270\text{ mm}$ (da base do conector à ponta) |
| **Diâmetro Estrutural Máximo** | $11\text{ mm}$ |
| **Peso Total Médio** | $\approx 58\text{ g}$ |
| **Conector Base** | SMA Fêmea (latão usinado dourado, encaixe direto sem adaptador) |
| **Condutor Radiante** | Cobre eletrolítico trançado (7 vias x 0,75 mm) |
| **Dielétrico** | Polietileno sólido compacto (não colapsa com calor) |
| **Revestimento Externo** | Tubo termorretraível poliolefínico 3:1 de dupla parede com resina adesiva |

---

## 🔬 Engenharia e Arquitetura Construtiva

```
[ TOPO: Ponteira Vinil 8mm + PU40 interno ]
    │
    ▼
┌──────┐ ─── Cap protetor (anti-perfuração / estanqueidade)
│      │
│  ██  │ ─── Elemento Ativo Superior (~112 mm)
│  ██  │     [Condutor de cobre 7 vias + Dielétrico de Polietileno sólido]
│  ██  │
├──────┤ ─── Ponto de Transição / Feedpoint (Sem resina externa)
│▒▒▒▒▒▒│
│▒▒▒▒▒▒│ ─── Haste Inferior / Luva Coaxial (160 mm a partir do conector)
│▒▒▒▒▒▒│     [Malha de cobre exposta e preservada, sem inversão]
│▒▒▒▒▒▒│
├──────┤
│░░░░░░│ ─── Base Livre (30 mm) [Cabo original íntegro]
└──────┘
  ║══║   ─── Conector SMA Fêmea (rosca externa, pino receptor central)
```

### Decisões de Projeto

* **Por que RG-213 e não LMR-240 / LMR-400?**  
  O LMR-240/400 padrão utiliza condutor central de cobre rígido e dielétrico de espuma injetada a gás. Em uma antena de rádio portátil submetida a flexão contínua, o condutor sólido quebra por fadiga rapidamente. Além disso, o calor do soprador térmico colapsa a espuma celular. O RG-213 com alma multifilar de 7 vias e dielétrico de polietileno sólido suporta milhares de ciclos de flexão sem fadiga e tolera o encolhimento térmico da capa sem perder a concentricidade dos $50\ \Omega$.
* **Monopolo com Luva sem Inversão de Malha:**  
  Não é realizada a inversão (rebate do avesso) da malha sobre o cabo. A malha pesada de cobre estende-se linearmente a partir do conector por 160 mm, criando uma luva de desacoplamento de RF uniforme que anula as correntes de modo comum no chassi do HT e minimiza o efeito capacitivo da mão do operador.
* **Isolamento de PU40:**  
  O selante estrutural PU40 é aplicado exclusivamente na cavidade interna da ponteira de vinil de 8 mm no topo. O ponto de transição (feedpoint) é mantido limpo sob o termorretrátil para evitar excesso de peso, bolhas de ar e variações de permissividade dielétrica.

---

## 📊 Validação em Bancada (NanoVNA-F / VNAmate)

Todas as unidades passam por varredura de calibração vetorial entre **420.000 MHz e 460.000 MHz** (Span de 40 MHz) antes da liberação.

### Dados Extraídos da Amostra Padrão (VNAmate):

| Frequência | SWR (ROE) | Return Loss | Mismatch | Impedância $Z$ | $|Z|$ | Fase $S_{11}$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **430.400 MHz** | 1.47 | 14.5 dB | 0.2 dB | $44.8\ \Omega + j17.4\ \Omega$ | $48.0\ \Omega$ | $96.1^\circ$ |
| **432.000 MHz** | 1.43 | 15.0 dB | 0.1 dB | $44.9\ \Omega + j16.2\ \Omega$ | $47.7\ \Omega$ | $97.8^\circ$ |
| **434.000 MHz** | 1.40 | 15.6 dB | 0.1 dB | $44.6\ \Omega + j14.9\ \Omega$ | $47.0\ \Omega$ | $101.2^\circ$ |
| **435.200 MHz** 🎯 | **1.37** | **16.1 dB** | **0.1 dB** | **$43.9\ \Omega + j13.6\ \Omega$** | **$46.0\ \Omega$** | **$105.9^\circ$** |
| **436.000 MHz** | 1.38 | 15.9 dB | 0.1 dB | $44.3\ \Omega + j14.1\ \Omega$ | $46.4\ \Omega$ | $103.7^\circ$ |
| **437.200 MHz** | 1.38 | 16.3 dB | 0.1 dB | $43.4\ \Omega + j12.9\ \Omega$ | $45.3\ \Omega$ | $109.2^\circ$ |
| **438.400 MHz** | 1.36 | 16.3 dB | 0.1 dB | $42.7\ \Omega + j12.4\ \Omega$ | $44.5\ \Omega$ | $112.6^\circ$ |
| **440.000 MHz** | 1.37 | 16.1 dB | 0.1 dB | $41.8\ \Omega + j11.8\ \Omega$ | $43.5\ \Omega$ | $117.3^\circ$ |
| **442.000 MHz** | 1.39 | 15.7 dB | 0.1 dB | $40.5\ \Omega + j11.5\ \Omega$ | $42.1\ \Omega$ | $122.4^\circ$ |

---

## 🛠️ Lista de Materiais (BOM)

* **Cabo Coaxial:** RG-213 $50\ \Omega$ homologado, alma multifilar (7 fios de cobre estanhado/nu), dielétrico de PE compacto, malha densa de cobre $> 95\%$.
* **Conector:** SMA Fêmea (corpo usinado em latão dourado, rosca externa, furo receptor central de 50 ohms).
* **Isolação e Acabamento:**
  * Tubo termorretraível 3:1 de dupla parede com adesivo interno vulcanizante (diâmetro nominal de contração compatível com 11 mm).
  * Anel de travamento mecânico na base (termorretrátil preto).
* **Proteção Superior:**
  * Ponteira de vinil flexível (Cap) de 8 mm diâmetro interno.
  * Resina adesiva selante de poliuretano (PU40) para preenchimento interno da ponta.

---

## 📐 Dimensões de Corte e Montagem

1. **Corte Inicial do Cabo:** Cortar o segmento de RG-213 no comprimento total de espera (~265 a 270 mm a partir da base do conector soldado).
2. **Base de Travamento:** Preservar os primeiros **30 mm** do cabo com capa preta intacta a partir do conector.
3. **Seção da Luva Coaxial (160 mm):** Decapar a capa externa de PVC mantendo a malha de cobre trançada exposta e esticada linearmente por 160 mm (contados a partir da base do conector).
4. **Elemento Ativo Superior (~120 mm):** Remover a malha externa a partir dos 160 mm, expondo apenas o dielétrico de polietileno sólido com a alma de cobre interna.
5. **Ajuste Fino de Bancada (Espera Capacitiva):** Cortar o condutor ativo em passos de 1 mm acompanhando o VNA até que a ressonância atinja 435.2–437.2 MHz. A colocação final do *cap* de vinil e do termorretrátil puxará a capacitância distribuída, cravando o centro em **435.000 MHz** com ROE de **1.37**.

---

## 🛡️ Política de Garantia

* **Cobertura (90 dias):** Defeitos ocultos de fabricação de bancada, incluindo quebra de continuidade na conectorização interna, solda fria ou degradação do isolamento dielétrico sem causa externa.
* **Comprovação Paramétrica:** Cada antena é registrada com os dados de SWR/Return Loss no momento da montagem.
* **Exclusões Absolutas:**
  * Danos por alavanca ou cisalhamento mecânico no conector SMA decorrentes de queda do aparelho.
  * Violação, perfuração ou corte do termorretrátil e da ponteira plástica.
  * Esmagamento da haste por prensagem mecânica externa.

---

## ⚖️ Aviso Regulatório (Anatel)

A faixa de **430 a 440 MHz** no Brasil é atribuída ao **Serviço de Radioamador** (conforme resolução e planos de atribuição da Anatel). A operação de transmissão requer licença válida (Certificado de Operador de Estação de Radioamador) e observância das potências e modos autorizados.

---

## 🌐 Site Oficial e Contato

* **Landing Page:** [lenda-435.github.io](https://lenda-435.github.io/)
* **Projeto & Repositório:** [github.com/lenda-435/lenda-435.github.io](https://github.com/lenda-435/lenda-435.github.io)
* **Atendimento e Pedidos:** Via WhatsApp através do botão oficial disponível na landing page.

---

<div align="center">
  <sub>Desenvolvido com rigor técnico de RF · São Luís, Maranhão</sub>
</div>