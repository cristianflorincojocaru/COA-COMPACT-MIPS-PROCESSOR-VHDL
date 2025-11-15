# Computer Organization and Architecture - COMPACT MIPS PROCESSOR VHDL

# 🧠 Compact MIPS Processor (VHDL)

Un procesor **MIPS redus** (Compact MIPS) implementat în **VHDL**, dezvoltat ca parte a proiectului de *Computer Organization and Architecture (COA)*. Acest design include componentele esențiale ale unui CPU MIPS: ALU, banc de registre, memorie de instrucțiuni, memorie RAM și unitate de control.

---

## 📑 Cuprins

- [Descriere](#descriere)
- [Funcționalități](#funcționalități)
- [Arhitectură](#arhitectură)
- [Tehnologii & Unelte](#tehnologii--unelte)
- [Structura proiectului](#structura-proiectului)
- [Instalare & Simulare](#instalare--simulare)
- [Exemplu de utilizare](#exemplu-de-utilizare)
- [Limitări cunoscute](#limitări-cunoscute)
- [Roadmap](#roadmap)
- [Contribuții](#contribuții)
- [Licență](#licență)

---

## 📝 Descriere

Proiectul reprezintă implementarea unui **procesor MIPS redus**, proiectat pentru a exemplifica funcționarea internă a unui procesor simplificat. Permite execuția unui subset de instrucțiuni MIPS de bază: operații aritmetice, logice, încărcări în memorie și instrucțiuni de branch.

Scopul este educațional și orientat spre înțelegerea arhitecturii la nivel **RTL (Register-Transfer Level)**.

---

## ⚙️ Funcționalități

- Unitate aritmetică și logică (**ALU**)  
- **Banc de registre** (Register File)  
- **Memorie instrucțiuni (ROM)** pentru program  
- **Memorie date (RAM)**  
- Execuție instrucțiuni **R-type și I-type**  
- **Branch condiționat**  
- Semnale de control și suport complet de simulare

---

## 🧱 Arhitectură

Arhitectura este inspirată din modelul standard **MIPS single-cycle**, fiind structurată în următoarele blocuri principale:

1. **PC + ROM** – aducerea instrucțiunilor
2. **Register File** – stocare temporară valori
3. **ALU** – execuție operații
4. **Memory Unit (RAM)** – citire/scriere
5. **Control Unit** – generare semnale control în funcție de opcode

---

## 🛠 Tehnologii & Unelte

| Componentă | Utilizat |
|-----------|---------|
| Limbaj descriere hardware | **VHDL** |
| Simulare | **ModelSim / GHDL / Vivado** |
| Vizualizare semnale | **GTKWave** |
| Platformă colaborare | **Git / GitHub** |

---

## 📁 Structura proiectului

```bash
├── src/
│   ├── alu.vhd
│   ├── register_file.vhd
│   ├── memory.vhd
│   ├── control.vhd
│   ├── pc.vhd
│   └── top.vhd
├── tb/
│   └── tb_top.vhd
├── programs/
│   └── test_program.mem
├── docs/
│   └── (diagrame și resurse)
└── LICENSE
