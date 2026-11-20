<div align="center">

<img src="assets/banner.svg" alt="RTS Downloads — Ferramentas Modbus da RTS Soluções em Elétrica e Automação" width="100%">

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logo-rts-dark.png">
  <img src="assets/logo-rts.png" alt="Logo RTS" width="110">
</picture>

### ⚡ Ferramentas gratuitas para testar, simular e integrar CLPs via Modbus

**Baixe, execute e conecte em minutos — sem cadastro, sem licença, sem complicação.**

<br>

[![Versão](https://img.shields.io/github/v/release/LaPumia1/rts-downloads?style=for-the-badge&label=vers%C3%A3o&color=F36523&labelColor=111111)](https://github.com/LaPumia1/rts-downloads/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/LaPumia1/rts-downloads/total?style=for-the-badge&label=downloads&color=F36523&labelColor=111111)](https://github.com/LaPumia1/rts-downloads/releases)
[![Modbus](https://img.shields.io/badge/Modbus-TCP%20%7C%20RTU-111111?style=for-the-badge&labelColor=F36523)](#-ferramentas-disponíveis)
[![Python](https://img.shields.io/badge/Python-3.9%2B-111111?style=for-the-badge&logo=python&logoColor=white&labelColor=F36523)](https://www.python.org/downloads/)
[![Windows](https://img.shields.io/badge/Windows-pronto-111111?style=for-the-badge&logo=windows&logoColor=white&labelColor=F36523)](#-começando-em-3-passos)

<br>

<a href="https://github.com/LaPumia1/rts-downloads/releases/latest">
  <img src="https://img.shields.io/badge/⬇%20%20BAIXAR%20AGORA-F36523?style=for-the-badge&labelColor=F36523" alt="Baixar agora" height="44">
</a>
&nbsp;
<a href="https://www.rtseletrica.com.br/">
  <img src="https://img.shields.io/badge/🌐%20%20SITE%20DA%20RTS-111111?style=for-the-badge" alt="Site da RTS" height="44">
</a>

</div>

<br>

---

## 🧰 Ferramentas disponíveis

<table>
<tr>
<td width="50%" valign="top">

### 🖥️ PyModbus

**Mestre e escravo Modbus com interface gráfica.**

Atue como **cliente/mestre** (TCP ou RTU) para ler e escrever em qualquer equipamento, ou **simule um servidor Modbus** completo com banco de memória editável — perfeito para testar sem ter o CLP na bancada.

- ✅ Modbus **TCP** e **RTU** (serial)
- ✅ Modo **mestre** e modo **servidor**
- ✅ Memória editável em tempo real
- ✅ Interface gráfica, sem linha de comando

<p align="center">
<a href="https://github.com/LaPumia1/rts-downloads/releases/latest/download/PyModbus.rar"><img src="https://img.shields.io/badge/⬇%20Baixar%20PyModbus.rar-~32%20MB-F36523?style=for-the-badge&labelColor=111111" alt="Baixar PyModbus"></a>
</p>

</td>
<td width="50%" valign="top">

### 🔌 RTS Modbus Bridge

**Liga o Simulador de CLP do site a um servidor Modbus real.**

Tudo que você muda no **Simulador de CLP Modbus** aparece no servidor Modbus — e tudo que um master externo escreve volta para a página, **ao vivo**.

- ✅ Compatível com **Modbus Mechanic** e outros masters
- ✅ Coils, entradas discretas, input e holding registers
- ✅ Sincronização bidirecional instantânea
- ✅ Leve: apenas ~15 KB em Python puro

<p align="center">
<a href="https://github.com/LaPumia1/rts-downloads/releases/latest/download/rts_modbus_bridge.zip"><img src="https://img.shields.io/badge/⬇%20Baixar%20rts__modbus__bridge.zip-~15%20KB-F36523?style=for-the-badge&labelColor=111111" alt="Baixar RTS Modbus Bridge"></a>
</p>

</td>
</tr>
</table>

---

## 🔄 Como a ponte funciona

```mermaid
flowchart LR
    A["🌐 Simulador de CLP<br/>(navegador)"] <-- "WebSocket<br/>ws://localhost:8765" --> B["🔌 RTS Modbus Bridge<br/>(Python)"]
    B <-- "Modbus TCP :502<br/>ou RTU (COM)" --> C["🖥️ Modbus Mechanic<br/>PyModbus · SCADA · CLP"]

    style A fill:#111111,stroke:#F36523,stroke-width:2px,color:#ffffff
    style B fill:#F36523,stroke:#111111,stroke-width:2px,color:#111111
    style C fill:#111111,stroke:#F36523,stroke-width:2px,color:#ffffff
```

---

## 🚀 Começando em 3 passos

> [!TIP]
> Precisa apenas do **[Python 3.9 ou mais novo](https://www.python.org/downloads/)** instalado (marque *“Add Python to PATH”* na instalação).

**1️⃣ Instale as dependências** (só na primeira vez), dentro da pasta extraída:

```bash
pip install -r requirements.txt
```

**2️⃣ Inicie a ponte** e deixe a janela aberta:

```bash
python rts_modbus_bridge.py
```

```text
Pagina web (WebSocket): ws://localhost:8765
Servidor Modbus TCP:    0.0.0.0:502
```

**3️⃣ Conecte tudo:**

| Onde | O que fazer |
|---|---|
| 🌐 **Simulador de CLP** | Abra ou recarregue (`F5`) a página — deve aparecer **🟢 Conectado à ponte Modbus local** |
| 🖥️ **Modbus Mechanic / master** | IP **`127.0.0.1`** (ou o IP do PC na rede) · Porta **`502`** · Slave ID **`1`** |

> [!IMPORTANT]
> No Windows, a porta **502** pode exigir executar o terminal **como Administrador**. Se o firewall perguntar, permita o acesso na rede privada.

---

## ❓ Dúvidas frequentes

<details>
<summary><b>Como abro o arquivo <code>.rar</code>?</b></summary>
<br>
Use o <a href="https://www.7-zip.org/">7-Zip</a> (gratuito) ou o WinRAR. No Windows 11 atualizado, o próprio Explorador de Arquivos já abre <code>.rar</code>.
</details>

<details>
<summary><b>O simulador não mostra “Conectado à ponte”.</b></summary>
<br>
Confira se a janela do <code>rts_modbus_bridge.py</code> continua aberta e sem erros, e recarregue a página com <code>F5</code>. A ponte usa a porta <code>8765</code> — ela não pode estar em uso por outro programa.
</details>

<details>
<summary><b>Posso usar Modbus RTU (serial) em vez de TCP?</b></summary>
<br>
Sim. Edite a variável <code>RTU_PORT</code> no início do <code>rts_modbus_bridge.py</code> (ex.: <code>"COM3"</code> no Windows ou <code>"/dev/ttyUSB0"</code> no Linux).
</details>

<details>
<summary><b>Dá para acessar a ponte de outro computador?</b></summary>
<br>
Sim. O servidor escuta em <code>0.0.0.0:502</code>; basta usar o IP da máquina onde a ponte está rodando, na mesma rede.
</details>

---

## 🏭 Sobre a RTS

<table>
<tr>
<td width="120" align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logo-rts-dark.png">
  <img src="assets/logo-rts.png" alt="Logo RTS" width="96">
</picture>
</td>
<td>

**RTS Soluções em Elétrica e Automação** — manutenção preventiva em máquinas industriais, montagem de painéis elétricos, SPDA, programação de CLP e desenvolvimento de software para automação.

🌐 [rtseletrica.com.br](https://www.rtseletrica.com.br/) &nbsp;·&nbsp; ✉️ [comercial@rtseletrica.com.br](mailto:comercial@rtseletrica.com.br)

</td>
</tr>
</table>

<div align="center">

<br>

**Gostou das ferramentas? Deixe uma ⭐ no repositório!**

<sub>Feito com ⚙️ e ⚡ pela equipe RTS</sub>

</div>
