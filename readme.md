### Aplicação de Backup - MudBlazor

	Esta aplicação fornece uma interface de usuário para fazer backup de arquivos de um diretório especificado usando o MudBlazor, uma biblioteca de componentes Blazor. Os usuários podem selecionar os caminhos de origem e destino para o backup, e a aplicação também integra-se ao Git para exibir informações sobre arquivos modificados cometidos por um autor específico.

### Funcionalidades

	Validação de Diretório: Os usuários podem inserir um diretório de origem, e a aplicação valida se o diretório existe antes de permitir que prossigam.

	Integração com Git: Lê automaticamente o .gitconfig do usuário para extrair seu nome e email, e lista os arquivos modificados por esse usuário no repositório localizado no caminho de origem.

	Seleção de Arquivos para Backup: Exibe uma lista de arquivos que foram modificados pelo usuário, permitindo que ele selecione quais arquivos deseja fazer backup.

	Interface Amigável: Utiliza componentes MudBlazor como MudCard, MudTextField e MudExpansionPanel para criar uma interface intuitiva e responsiva.
	
### Visão Geral da Página

A página principal da interface do usuário é estruturada usando componentes do MudBlazor:

	1. Cartão de Informações de Backup: Exibe campos para inserir os diretórios de origem (caminhoOrigem) e destino (caminhoDestino) para o backup.
	1.1 Um botão rotulado Iniciar Backup é exibido assim que os diretórios são validados, permitindo que o processo de backup seja iniciado.

	2. Cartão de Informações do Usuário: Exibe o nome e o email do usuário, extraídos do seu arquivo .gitconfig.

	3. Lista de Arquivos Modificados: Exibe uma lista de arquivos modificados pelo autor selecionado, usando um painel expansível (MudExpansionPanel). Os usuários podem selecionar arquivos específicos para fazer backup.
	
### Componentes Utilizados

	MudGrid & MudItem: Para layout responsivo, organizando os campos de entrada e os cartões de informações.

	MudCard: Para agrupar visualmente informações relacionadas, tornando a interface mais organizada e atraente.

	MudTextField: Para capturar os caminhos de origem e destino.

	MudAlert: Exibe mensagens de erro relacionadas a caminhos inválidos ou informações de configuração do Git ausentes.

	MudButton: Aciona o processo de backup.

	MudExpansionPanel: Lista expansível para visualizar e selecionar arquivos modificados para backup.

	MudCheckBox: Para selecionar arquivos individualmente.
	
### Como Usar

	1. Digite o Caminho de Origem: Forneça o caminho do diretório que deseja fazer o backup.
	1.1 A aplicação valida se o caminho inserido existe. Se não, um alerta de erro é exibido.

	2. Digite o Caminho de Destino: Depois que o caminho de origem é validado, insira o caminho de destino para o backup.

	3. Iniciar o Backup: Clique no botão Iniciar Backup para prosseguir.

	4. Ver Informações do Usuário: A aplicação extrairá o nome e o email do .gitconfig do usuário e exibirá na interface.

	5. Selecionar Arquivos para Backup: Veja a lista de arquivos modificados pelo autor atual do Git e use as caixas de seleção para escolher os arquivos que deseja fazer backup.

### Requisitos

	MudBlazor: A interface é construída usando componentes do MudBlazor, então certifique-se de que o MudBlazor está instalado e referenciado no seu projeto.

	Git: A aplicação depende do arquivo .gitconfig para extrair o nome e o email do usuário atual. Certifique-se de que o Git está configurado corretamente na máquina.
	
### Executando a Aplicação

	1. Clone o repositório.

	2. Instale as dependências e restaure o projeto.

	3. Execute a aplicação Blazor usando o Visual Studio ou a linha de comando.

### Estrutura do Projeto

	Pages/Backup.razor: A página principal para a funcionalidade de backup.

	Classe ArquivoAlterado: Representa os arquivos modificados com as propriedades Nome e Selecionado.

	Métodos de Validação e Backup: A lógica para validar os caminhos e iniciar o processo de backup está incluída no bloco @code da página.
	
### Tratamento de Erros

	Caminhos Inválidos: Exibe um erro se o diretório de origem não for válido.

	Configuração do Git Não Encontrada: Exibe um erro se o arquivo .gitconfig estiver ausente ou se não contiver user.name ou user.email.
	
### Melhorias Futuras

	Indicador de Progresso: Adicionar uma barra de progresso para mostrar o status do processo de backup.

	Suporte a Múltiplos Usuários: Permitir a seleção de diferentes usuários do Git em um dropdown.

	Agendamento de Backups: Fornecer uma opção para agendar backups automáticos.
	
### Licença

	Este projeto é licenciado sob a Licença MIT - veja o arquivo LICENSE para mais detalhes.

### Contribuindo

	Pull requests são bem-vindos. Para grandes mudanças, por favor, abra um problema primeiro para discutir o que você gostaria de mudar.

### Agradecimentos

	Documentação do MudBlazor por fornecer guias detalhados e exemplos.