# Introdução aos sistemas operacionais


## 1. Pequena Timeline da Evolução dos Sistemas Operacionais (SOs)

A evolução dos sistemas operacionais acompanha diretamente o desenvolvimento do hardware, saindo de máquinas gigantescas que rodavam um programa por vez para os smartphones em nossos bolsos.

- **Anos 1940 (A Era sem SO):**  
  Os primeiros computadores não tinham sistema operacional. Os programadores interagiam diretamente com o hardware usando painéis de plugues e cartões perfurados.

- **Anos 1950 (Processamento em Lote / Batch):**  
  Surgem os primeiros SOs rudimentares. Os trabalhos (*jobs*) eram agrupados e executados em lote para reduzir o tempo de ociosidade das caras máquinas da época (ex: GM-NAA I/O).

- **Anos 1960 (Multiprogramação e Tempo Compartilhado):**  
  A CPU passa a ser alternada rapidamente entre vários usuários e tarefas. Surgem sistemas icônicos como o Multics e o nascimento do Unix (1969).

- **Anos 1970/1980 (Computadores Pessoais):**  
  O foco muda para o usuário doméstico. Surgem interfaces de linha de comando simplificadas como o MS-DOS e as primeiras Interfaces Gráficas de Usuário (GUI) com o Mac OS da Apple e, posteriormente, o Windows.

- **Anos 1990 (Código Aberto e Redes):**  
  O Linux (1991) é criado, democratizando o acesso a um SO robusto e de código aberto. O Windows 95 populariza de vez o PC doméstico conectado à internet.

- **Anos 2000 em diante (Era Mobile e Nuvem):**  
  O surgimento dos smartphones traz o iOS e o Android (baseado em Linux). Os SOs passam a ser altamente integrados com a computação em nuvem (ex: ChromeOS).

![](https://frankalcantara.com/assets/images/timeline_evolutivo_so.webp)
---

## 2. Principais Conceitos

Para entender como um SO funciona, é essencial dominar seu vocabulário básico:

- **Kernel (Núcleo):**  
  É o coração do sistema operacional. É a parte do código que está sempre rodando na memória, com controle total sobre o sistema, gerenciando as interações mais baixas com o hardware.

- **Processo:**  
  É um programa em execução. Se você abre o navegador duas vezes, está rodando o mesmo programa, mas o SO cria dois processos independentes.

- **Thread (Fio de execução):**  
  Uma subdivisão de um processo. Um processo pode ter várias threads rodando paralelamente (ex: uma thread carrega a imagem de um site enquanto outra carrega o texto).

- **System Calls (Chamadas de Sistema):**  
  É a interface (a "porta") que os programas de usuário usam para pedir serviços ao Kernel (como ler um arquivo ou conectar à internet), garantindo que os programas não acessem o hardware diretamente.

- **Modo Usuário vs. Modo Kernel:**  
  Uma separação de privilégios de hardware. Aplicativos rodam no Modo Usuário (com limitações). Quando precisam de algo crítico, pedem ao SO, que executa no Modo Kernel (acesso total).

- **BATCH:**  
  Processamento em lote, usado para enfileirar tarefas;

- **SPOOLING:**  
  Processo de transferência de dados, colocando-os em uma área de trabalho temporária em que outro programa poderá acessá-lo.

- **TIME-SHARING:**  
  Tempo repartido que utiliza multiprogramação dividindo o tempo de processamento da CPU entre os processos ativos.

- **TIME-SLICE:**  
  Uma fatia de tempo do time-sharing.

- **REAL-TIME:**  
  Sistema com tempo de resposta predefinidos.
 

---

## 3. Principais Funções e o Que Elas Resolveram

Os sistemas operacionais foram criados para resolver problemas graves de eficiência, organização e segurança das máquinas antigas.

| Função do SO | O que faz | Problema que resolveu |
|--------------|-----------|---------------------|
| **Gerenciamento de Processos** | Cria, agenda e encerra processos, decidindo quem usa a CPU e por quanto tempo (Escalonamento). | Ociosidade da CPU e Monotarefa: Resolveu o problema do computador só poder fazer uma coisa por vez, criando a ilusão de que vários programas rodam ao mesmo tempo. |
| **Gerenciamento de Memória** | Controla qual parte da memória RAM está em uso e por quem, usando técnicas como Memória Virtual e Paginação. | Conflitos de dados e Memória limitada: Impediu que um programa sobrescrevesse os dados do outro e permitiu rodar programas maiores que a memória RAM física disponível. |
| **Gerenciamento de Arquivos** | Cria, apaga e organiza os dados em diretórios (pastas) nos discos de armazenamento (HDDs, SSDs). | Caos dos discos físicos: Substituiu a necessidade de os programadores saberem em qual trilha e setor do disco uma informação estava gravada, abstraindo tudo em arquivos. |
| **Gerenciamento de Dispositivos (E/S)** | Lida com todos os periféricos através de *Device Drivers* (programas tradutores para hardware específico). | Incompatibilidade de hardware: Evitou que os desenvolvedores de software tivessem que escrever um código diferente para cada marca de impressora, teclado ou monitor existente no mercado. |
| **Segurança e Proteção** | Controla permissões de usuários e protege os recursos do sistema contra acessos não autorizados. | Vulnerabilidade total: Impediu que usuários ou programas maliciosos acessassem dados confidenciais de outras pessoas ou causassem a falha (crash) do sistema inteiro. |
