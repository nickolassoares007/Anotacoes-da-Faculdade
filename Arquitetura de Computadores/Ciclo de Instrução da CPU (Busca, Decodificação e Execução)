## 📌 O que é o Ciclo de Instrução?

O ciclo **buscar-decodificar-executar** descreve a operação básica dos sistemas computacionais modernos. É o processo básico que a **CPU** realiza para **executar qualquer programa**.  
Cada comando de um programa passa por três grandes etapas:

> **Busca → Decodificação → Execução**

Esse ciclo se repete **milhões ou bilhões de vezes por segundo**, coordenado pelo **clock** do processador.

![](https://adacomputerscience.org/images/content/computer_science/computer_systems/architecture/figures/ada_cs_arch_cpu_fde.svg)

---

## 🔁 1. Etapa de Busca (Fetch)

### O que acontece?
- A **CPU busca a próxima instrução** que está armazenada na memória RAM.
- O endereço da próxima instrução está no **Contador de Programa (PC — Program Counter)**.

#### Para **buscar** uma instrução da memória principal:

1. O contador de programa (PC) armazena o endereço da próxima instrução a ser executada. O conteúdo do PC é copiado para o registrador de endereço de memória (MAR), que está conectado ao barramento de endereços. O **endereço** da próxima instrução a ser executada é colocado no **barramento de endereços** .

![](https://adacomputerscience.org/images/content/computer_science/computer_systems/architecture/figures/ada_cs_arch_proc_pc_to_mar.svg)

2. Uma vez que o endereço da instrução esteja no barramento de endereços, a unidade de controle instrui uma operação **de leitura de memória** para permitir que o conteúdo do local de memória seja transferido para o processador. A **instrução** armazenada nesse endereço é transferida usando o **barramento de dados** da memória principal para o **processador** e salva no registrador de buffer de memória (MBR)/registrador de dados de memória (MDR).
    
    Simultaneamente, o conteúdo do contador de programa (PC) é incrementado em um para que aponte para o endereço da próxima instrução que precisa ser buscada.
    

Em um programa sequencial, a próxima instrução a ser executada normalmente é mantida no local de memória seguinte. É por isso que o PC é incrementado em um. No entanto, se a próxima instrução envolver uma ramificação para outro local do programa, o PC será adaptado para apontar para o endereço correto.

![](https://adacomputerscience.org/images/content/computer_science/computer_systems/architecture/figures/ada_cs_arch_proc_main_to_mbr.svg)
3. O conteúdo do registrador de buffer de memória (MBR)/registrador de dados de memória (MDR) é copiado para o registrador de instrução atual (CIR). Isso garante que a instrução atual seja mantida segura para que o registrador de buffer de memória (MBR)/registrador de dados de memória (MDR) possa ser usado durante o estágio de execução, para armazenar dados adicionais necessários.
![](https://adacomputerscience.org/images/content/computer_science/computer_systems/architecture/figures/ada_cs_arch_proc_mbr_to_cir.svg)

### Componentes envolvidos:
- **PC (Program Counter):**  Armazena o endereço da **próxima instrução** a ser buscada na memória.
- **MAR (Memory Address Register):**  Recebe o endereço enviado pelo PC e o envia ao **barramento de endereços** para buscar na memória o conteúdo localizado ali.
- **MBR / MDR (Memory Buffer Register / Memory Data Register):**  Armazena temporariamente o **dado** ou **instrução** que veio da memória (ou que será gravado nela). Pode tanto receber da memória quanto enviar para ela.
- **IR / CIR (Instruction Register / Current Instruction Register):** Armazena a **instrução atual** que foi buscada e que está prestes a ser **decodificada** e **executada**.
- **Barramento de endereços:** envia esse endereço até a memória.
- **Memória RAM:** retorna o conteúdo daquele endereço.
- **Registrador de Instrução (IR):** armazena temporariamente a instrução buscada.

### Exemplo:
- PC = 0x0010 → CPU acessa RAM[0x0010] → IR recebe a instrução.

---

## 🧩 2. Etapa de Decodificação (Decode)

### O que acontece?
- A **Unidade de Controle (UC)** analisa a instrução armazenada no registrador IR.
- A CPU identifica qual operação deve ser realizada (ex: soma, carga de dado, salto).

#### Estágio de decodificação

1. A unidade de controle decodifica a instrução que é mantida no registrador de instruções atual (CIR).
2. Isso envolve dividir a instrução em ==operando e opcode== para determinar que tipo de instrução precisa ser executada.
3. Se o operando especificar um local de memória, o estágio de decodificação pode incluir o início do processo para buscar os dados necessários para a execução da instrução.
4. Pode ser necessário configurar ou inicializar registradores ou sinalizadores internos com base na instrução que está sendo executada.
5. A unidade de controle gera sinais de controle específicos com base na instrução decodificada. Esses sinais de controle instruem vários componentes do processador a executar a instrução.

![](https://adacomputerscience.org/images/content/computer_science/computer_systems/architecture/figures/ada_cs_arch_proc_decode.svg)

### Componentes envolvidos:
- **UC (Unidade de Controle):** interpreta o código binário da instrução.
- **Decodificador de instrução:** quebra a instrução em partes (opcode + operandos)
- Define quais sinais de controle precisam ser ativados (registradores, ULA, memória etc).

### Exemplo:
- Instrução: `LOAD R1, [0x0040]`  
- A CPU entende que deve **carregar** o conteúdo da posição de memória `0x0040` para o registrador `R1`.

---

## ⚙️ 3. Etapa de Execução (Execute)

### O que acontece?
- A CPU **executa a operação solicitada** pela instrução decodificada.
- Pode ser uma operação aritmética, lógica, movimentação de dados ou desvio de fluxo.

#### Estágio de execução

1. A instrução é executada. A sequência exata de operações depende do tipo de instrução que está sendo executada. Por exemplo, para uma instrução aritmética (como somar dois números), todos os dados necessários são buscados na memória principal, o cálculo é executado pela Unidade Lógica e Aritmética (ULA), e o resultado da instrução é armazenado no acumulador, em um registrador de uso geral, ou de volta na memória principal.

Caso o programa exija a execução de uma instrução não sequencial, por exemplo, se a instrução atual for um desvio neste estágio, o endereço da próxima instrução a ser executada é determinado e carregado no contador de programa (PC).

![](https://adacomputerscience.org/images/content/computer_science/computer_systems/architecture/figures/ada_cs_arch_proc_execute.svg)

### Componentes envolvidos:
- **ULA (Unidade Lógica e Aritmética):** faz cálculos e comparações.
- **Registradores:** armazenam dados temporários para operações.
- **Barramento de dados:** transfere dados entre memória e CPU.
- **Memória RAM:** pode ser acessada para leitura ou escrita.

### Exemplos de execução:
- `ADD R1, R2 → R3`: soma o conteúdo de R1 e R2, resultado vai para R3.
- `JUMP 0x0100`: altera o PC para 0x0100, mudando o fluxo do programa.

---

## 🔄 4. Repetição do Ciclo

Depois de executar a instrução:
- O **Program Counter (PC)** é incrementado para apontar para a próxima instrução.
- O ciclo se repete: **Busca → Decodifica → Executa**

---

## 🧠 Visão Resumida do Fluxo

```plaintext
[PC] → Endereço da instrução
 ↓
[Memória] → Instrucao carregada no IR
 ↓
[UC] → Decodifica e ativa componentes
 ↓
[ULA / Registradores / Memória] → Executam a operação
 ↓
[PC + 1] → Próxima instrução
