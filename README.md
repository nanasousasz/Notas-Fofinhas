<<<<<<< HEAD
# Notas Fofinhas

Aplicativo de **notinhas na área de trabalho** para Windows, feito com [Electron](https://www.electronjs.org/). Cada nota é uma janela pequena, sem moldura, com tema pixel art, texto livre ou lista de tarefas (to-do), cores e posição salvas automaticamente.

---

## Como funciona o bloco de notas

1. **Bandeja do sistema (systray)**  
   Ao abrir o app, aparece o ícone **Notinhas Fofinhas**. Por ali você cria notas novas, vê quantas estão abertas, envia todas para frente ou para trás, oculta ou mostra todas e encerra o programa.

2. **Cada nota**  
   - **Arrastar:** segure pelo topo (cabeçalho) e mova pela tela. A posição é gravada em `notes.json` na pasta de dados do app.  
   - **Cores:** botão da paleta no canto superior direito.  
   - **Texto / To-do:** botão no canto inferior direito alterna entre anotação livre e lista de tarefas.  
   - **Ocultar / apagar / nova:** ícones no topo da nota (conforme os tooltips na interface).  
   - **Dicas:** botão de ajuda no cabeçalho.

3. **Atalhos úteis**  
   - **Win+D** — no Windows, “Mostrar área de trabalho” costuma minimizar janelas normais; as notas deste app foram pensadas para **continuar visíveis** como widgets no desktop (veja a seção abaixo).  
   - **Ctrl+Alt+Q** — traz todas as notas **para frente** de outras janelas; pressionar de novo devolve ao comportamento padrão (atrás dos outros programas, “grudadas” na camada do desktop).

4. **Início com o Windows**  
   O app pode iniciar junto com o Windows (opção configurada no código para abrir minimizado na bandeja).

5. **Atualizações**  
   Se o instalador/publicação definir a variável de ambiente `UPDATE_URL`, o app pode buscar atualizações automaticamente (via `electron-updater`).

---

## O que significa “deixar o bloco grudado na tela”

O Windows não oferece, para apps comuns, um modo oficial de “colar uma janela no papel de parede” como o Sticky Notes clássico ou gadgets antigos. Para as notas **parecerem parte do desktop** — por exemplo, **não sumirem** quando você usa **Win+D** (mostrar desktop) — o programa usa um script auxiliar: `pin-to-desktop.ps1`.

Esse script é chamado pelo app com **PowerShell** e faz ajustes de baixo nível na janela da nota, usando a API **Win32** do Windows, por exemplo:

- associa a janela ao **Progman** (a janela do programa “Program Manager”, ligada ao desktop que você vê);
- aplica estilos de janela do tipo **tool window**, para reduzir o efeito de “minimizar tudo” do shell sobre essas janelas;
- opcionalmente envia a janela para **trás** (`HWND_BOTTOM`), para ficar atrás das outras aplicações quando você não está no modo “todas na frente”.

Assim, as notas ficam na **camada visual do desktop**: úteis para lembretes sempre à vista ou logo abaixo das janelas que você usa no dia a dia.

---

## Por que o Windows (ou antivírus) pode “achar que é vírus”

Nada disso é malware por si só — é o mesmo tipo de técnica que **widgets**, **launchers** ou **ferramentas de overlay** usam. Porém, **heurísticas** de segurança costumam reagir a combinações como:

- executar **PowerShell** com política permissiva (`Bypass`) para rodar um script junto com o app;
- alterar **estilos estendidos** de janela e relações de **proprietário** com **Progman**;
- janelas **sem barra de título**, **transparentes**, **fora da barra de tarefas** e que **não se comportam** como uma janela “normal”.

Para o antivírus, isso pode parecer parecido com um programa que **se sobrepõe à tela** ou **manipula janelas** — comportamento que **vírus reais** também exploram. Por isso podem aparecer **avisos**, **SmartScreen** ou **falsos positivos**, principalmente em versões não assinadas ou pouco conhecidas.

**Em resumo:** a função “grudar na tela” existe para **experiência de post-it no desktop** e para **Win+D**; o custo é usar APIs avançadas que **disparam alertas** em alguns ambientes. O código-fonte do projeto (`main.js`, `pin-to-desktop.ps1`) mostra exatamente o que é executado — não há intenção oculta além de posicionar as notas na camada do desktop.

Se o Windows bloquear ou isolar o script, você pode precisar **permitir explicitamente** o app na pasta de instalação ou marcar como confiável **somente** se você confiar na origem do instalador.

---

## Desenvolvimento

```bash
npm install
npm start
```

Build do instalador Windows (NSIS / portable), conforme `package.json`:

```bash
npm run dist
```

---

## Arquivos principais

| Arquivo | Função |
|--------|--------|
| `main.js` | Processo principal Electron: janelas, bandeja, atalhos, persistência, chamada ao script de pin. |
| `note.html` | Interface de cada nota (texto, to-do, temas). |
| `pin-to-desktop.ps1` | Ajustes Win32 para “grudar” a janela na camada do desktop. |

---

*Notas Fofinhas — widget de notas na área de trabalho.*
=======
# Notas-Fofinhas
Meu primeiro aplicativo de computador. Notas Fofinhas!
>>>>>>> 394122d8446c96b3ee2f9afdda966452085dfb43
