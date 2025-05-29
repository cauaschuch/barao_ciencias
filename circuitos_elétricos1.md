# 🔌 Circuitos Elétricos - Parte 1: Entendendo o Caminho da Corrente

## 🚿 Relembrando a analogia da água

Se você chegou até aqui, já sabe que em um circuito elétrico a **tensão (voltagem)** funciona como a **pressão da água** e a **corrente elétrica** é como o **fluxo de água que passa pelo cano**.

Agora vamos dar um passo além: o que acontece quando ligamos uma bateria e fios condutores a componentes como LEDs e resistores?

## 🔋 A bateria empurra os elétrons

A função da **bateria** (ou qualquer outra fonte de tensão) é criar uma **diferença de potencial elétrico** entre seus dois polos, que **empurra os elétrons** através do circuito.

Esse “empurrão” é o que causa o movimento de elétrons — a **corrente elétrica** — pelos fios condutores até os dispositivos que serão alimentados.

> 💡 Pense assim: a bateria está "pressionando" os elétrons a seguir o caminho do fio, como uma bomba empurrando a água num cano.

📸 **Imagem**:  
![Imagem: Resistores em paralelo?](./IMAGES/resistores_paralelo)

---

# 🔌 Associações de Resistores

Depois de entender que a **corrente elétrica** é como um fluxo de água que passa por canos (os fios), vamos agora descobrir o que acontece quando colocamos **vários resistores** em um circuito.

Mas antes...  
## 🧩 Como são os símbolos dos circuitos?

Antes de construir qualquer circuito, usamos **símbolos** para representar os componentes em um desenho chamado **diagrama esquemático**.

- **Resistor:** é representado por um retângulo ou uma "ondinha" assim:

![Imagem: símbolo de resistor](./IMAGES/simbolo_resistor.png)

- **Fonte de tensão (bateria):** é representada por duas linhas, uma maior (polo positivo) e uma menor (polo negativo):

![Imagem: símbolo de bateria](./IMAGES/simbolo_bateria.png)

---

## 🧱 Resistores em Série

Quando colocamos resistores **um depois do outro**, dizemos que eles estão **em série**. É como se fossem várias barreiras seguidas no caminho da corrente elétrica.  
A corrente passa por todos eles, um por um, **sem se dividir**.

Veja o diagrama abaixo:

![Imagem: resistores em série](./IMAGES/resistores_em_serie.png)

> 💡 A corrente que passa por todos os resistores **é a mesma**.

A resistência total (ou equivalente), chamada de \( R_{\text{eq}} \), é a **soma de todas as resistências individuais**:

\[
R_{\text{eq}} = R_1 + R_2 + R_3 + \ldots + R_n
\]

Ou seja, é como se todos os resistores virassem **um só resistor grandão**!

---

## 🌊 Resistores em Paralelo

Agora, se colocamos os resistores **lado a lado**, em caminhos diferentes para a corrente passar, dizemos que eles estão **em paralelo**.  
É como se fossem **túneis diferentes para a água correr**!

Veja o diagrama:

![Imagem: resistores em paralelo](./IMAGES/resistores_em_paralelo.png)

> ⚡ A corrente **se divide** entre os caminhos, mas todos os resistores recebem a **mesma tensão**.

A resistência equivalente nesse caso é diferente. A fórmula é:

\[
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3} + \ldots + \frac{1}{R_n}
\]

Ou seja, quanto mais resistores em paralelo, **menor será a resistência total**. Parece mágica, mas é só física! 😊

---

## 🧪 Vamos testar na prática?

Você pode montar esses circuitos em simuladores como o Tinkercad e ver a corrente e a tensão em tempo real.  
É como brincar de montar e testar seus próprios experimentos de eletricidade!


