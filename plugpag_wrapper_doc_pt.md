# PlugPag Service
## Introdução
A biblioteca PlugPag Service Wrapper possui como objetivo expor o conjunto de funcionalidades existentes no serviço PlugPagService, este aplicativo está disponível em todas as Moderninhas Smart e X da PagSeguro.

## Pré requisitos
A biblioteca PlugPagService para o sistema operacional Android possui algumas restrições
para seu uso:
* A biblioteca PlugPag possui suporte da API level 25 (7.1.1 Nougat) à 28 (9.0 Pie),
devido às versões de Android presentes nos terminais Moderninha Smart e
Moderninha X.
* Apenas uma única instância do PlugPag deve existir durante o uso do aplicativo. A
existência de múltiplas instâncias pode fazer com que o comportamento seja
indeterminado.
* As chamadas dos métodos da classe PlugPag devem ser feitas em uma Thread que
execute em background pois podem demorar para finalizar a execução. Caso a
execução seja feita na Thread principal (UI Thread), o aplicativo pode apresentar um
ANR (Application Not Responding). Além disso, alguns métodos executam transações
utilizando chamadas remotas pela internet, o que impossibilita suas chamadas na
Thread principal.
* Eventos que chamem duas ou mais vezes o serviço de pagamento ou estorno antes
da operação ser finalizada, podem ocasionar comportamento anormal no serviço e
requerer que a aplicação seja fechada para realizar o unbind do serviço.
