Secretaria Escolar
Sistema de gestão escolar que roda inteiro no navegador, em um único arquivo: gestao-escolar.html.

Não tem servidor, banco de dados nem cadastro. Os dados ficam na memória da aba enquanto ela estiver aberta, e nada é enviado para a internet.

Importante: ao recarregar ou fechar a página, todos os dados são apagados. Antes de sair, use Início → Exportar backup para salvar um arquivo .json. Na próxima vez, use Importar backup para continuar de onde parou.

Como usar
Baixe o arquivo gestao-escolar.html.
Abra com dois cliques. Funciona melhor no Google Chrome ou no Microsoft Edge, em computador ou celular.
Na tela Início, digite o nome da escola e, se quiser, envie um logo ou qualquer imagem. Esse nome e essa imagem aparecem no menu, nos PDFs e nos bilhetes de rifa.
Para conhecer o sistema antes de usar com dados reais, clique em Carregar dados de exemplo. Depois use Limpar tudo para começar do zero.
É preciso internet na hora de abrir o arquivo, porque as bibliotecas de PDF e de detecção de rosto são baixadas de CDNs públicas (veja Bibliotecas usadas).

Módulos
1. Carômetro
Envie várias fotos de uma vez e informe a turma antes de enviar.
O nome do arquivo vira o nome do aluno. Formatos aceitos:
07 - Ana Souza.jpg → número 7, nome "Ana Souza"
Ana Souza - 7.jpg → número 7, nome "Ana Souza"
ana_souza.jpg → sem número, nome "Ana Souza"
O rosto é detectado e a foto é recortada automaticamente no formato 3x4.
Quando o rosto não é encontrado, a foto fica marcada com "Conferir". Clique no aluno e use Ajustar enquadramento para arrastar o quadro e dar zoom.
Edite nome, turma e número clicando no cartão do aluno.
Renumerar em ordem alfabética: filtre uma turma e o botão aparece.
Exportar: PDF (uma página por turma, de 4 a 7 fotos por linha) e JSON (inclui as fotos).
2. Mapa de Sala
Defina o número de fileiras e de carteiras por fileira.
Os alunos vêm automaticamente do Carômetro. Escolha a turma no seletor.
Arraste o aluno até a carteira. Arrastar de uma carteira para outra troca os dois de lugar, e arrastar de volta para "Sem lugar" tira o aluno da carteira.
No celular: toque no aluno e depois na carteira.
Preenchimento automático por número, em ordem alfabética ou aleatório.
Exportar/Importar JSON, para editar o mapa depois, e PDF em folha deitada com a lousa no topo.
3. Rifas
Crie a rifa com nome, prêmio, valor do número, quantidade, primeiro número, data do sorteio e chave Pix (opcional).
Os números são gerados automaticamente. Clique em um número para marcá-lo como vendido, com o nome do comprador, o telefone e se já pagou.
Marque Vender vários de uma vez para vender vários números para a mesma pessoa.
Um painel mostra os números vendidos e disponíveis, o valor arrecadado e quanto falta receber, além da tabela de compradores.
Sorteio com animação, entre os números vendidos. Também é possível incluir os não vendidos. Dá para sortear mais de um prêmio.
Exportar: lista em PDF (vendidos, disponíveis e resultado do sorteio), bilhetes com canhoto em PDF (5 por folha A4) e JSON.
4. Cantina e Produtos
Cadastre produtos com nome, preço, foto e estoque. Deixe o estoque em branco para não controlar quantidade.
Monte o carrinho, escolha a forma de pagamento e, se for em dinheiro, informe o valor recebido para calcular o troco.
As vendas ficam registradas por dia, e é possível cancelar uma venda (os itens voltam para o estoque).
PDFs: catálogo de produtos com foto, comprovante de venda (formato de bobina de 80 mm) e relatório de vendas do dia.
Exportar/Importar JSON de produtos e vendas.
5. Planejamento de Aulas
Cadastre turmas e disciplinas. As turmas valem para todo o sistema.
Cada aula tem data, turma, disciplina, aula/horário, conteúdo, objetivos, recursos e observações.
Veja as aulas em lista ou calendário. No calendário, clique em um dia para planejar uma aula naquela data.
Filtre por mês, turma e disciplina. O PDF sai com o que estiver filtrado.
Exportar/Importar JSON.
6. Abonadas e Substituições
Registre o pedido com professor, data, tipo (abonada, atestado, licença…), motivo, turmas e aulas afetadas.
Status: Pendente, Aprovada ou Rejeitada, com botões rápidos para aprovar ou rejeitar.
Para planejar a substituição, informe quem vai cobrir as aulas e a atividade deixada para a turma. O painel avisa quantas faltas futuras ainda não têm substituto.
Filtre por período, status e professor.
Relatório em PDF com linhas para a assinatura da direção e da coordenação, e JSON.
Recursos gerais
Tema claro e escuro (botão no menu).
Mensagens de confirmação e de erro, e validação dos campos obrigatórios.
Limpar tudo: apaga toda a memória da aplicação, depois de pedir confirmação.
Backup completo: um único JSON com todos os módulos.
Aviso do navegador se a página for fechada com dados na memória.
Publicar na internet (opcional)
Como é um arquivo HTML estático, ele pode ser hospedado gratuitamente, por exemplo no GitHub Pages:

Crie um repositório e envie gestao-escolar.html (e este README.md).
Se quiser que o sistema abra direto pelo endereço do site, renomeie o arquivo para index.html.
No repositório, vá em Settings → Pages, escolha a branch main e salve.
Mesmo publicado, cada pessoa que abre o site tem os próprios dados, só no navegador dela. Ninguém vê os dados de outra pessoa.

Privacidade
Fotos, nomes e demais dados nunca saem do computador. O processamento (recorte de fotos, PDFs, sorteios) é feito no próprio navegador.
O sistema só acessa a internet para baixar as bibliotecas listadas abaixo e as fontes do Google Fonts.
O único item gravado no navegador é a escolha de tema claro ou escuro.
Bibliotecas usadas
Biblioteca	Versão	Para que serve	Origem
jsPDF	2.5.1	Geração dos PDFs	cdnjs
jsPDF-AutoTable	3.8.2	Tabelas nos PDFs	cdnjs
face-api (modelo Tiny Face Detector)	1.7.13	Detecção de rosto no carômetro (carregada só quando você envia fotos)	jsDelivr
Inter e Bricolage Grotesque	—	Fontes da interface	Google Fonts
Limitações conhecidas
Sem internet, os PDFs não são gerados e as fotos não são enquadradas automaticamente (ficam centralizadas). O resto do sistema continua funcionando.
Fotos no formato HEIC (padrão do iPhone) não são lidas. Converta para JPG antes de enviar.
Muitas fotos ocupam bastante memória. Turmas grandes funcionam bem, mas centenas de fotos de uma vez podem deixar o navegador lento em computadores mais simples.
Os comprovantes da cantina não têm valor fiscal.
Para quem quiser modificar o código
Tudo está em gestao-escolar.html, dividido em blocos comentados:

Bloco	Conteúdo
<style>	Cores do tema (variáveis em :root), layout e componentes
1. Estado em memória	Objeto state com todos os dados (freshState() define a estrutura)
2. Utilitários	Datas, moeda, toasts, modais, download e importação de arquivos
3. Imagens e detecção de rosto	Redução, recorte 3x4 e uso do face-api
4. PDF	Cabeçalho, rodapé e estilos de tabela padrão
6–11. Módulos	Car, SeatMap, Rifa, Cantina, Plan, Abon
12. Aplicação	Navegação, tela inicial, tema, backup, dados de exemplo e "Limpar tudo"
Cada módulo tem init() (liga os botões) e render() (redesenha a tela). Depois de alterar o state, chame App.refresh() para atualizar tudo.
