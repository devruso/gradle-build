
### WindCharge Plugin

## Descrição

O plugin **WindCharge** para Minecraft permite aos jogadores modificar as propriedades de velocidade, explosão e geração de partículas do item Wind Charge, assim como permite aos jogadores criar e gerenciar "homes" dentro do jogo. Com funcionalidades adicionais, como cooldowns e partículas, o plugin oferece uma maneira conveniente e personalizada de modificar aspectos do item, mas também armazenar e teletransportar-se para locais específicos no mundo do Minecraft.

## Funcionalidades

- **Criar e Gerenciar Homes**: Comandos para definir homes e teletransportar para elas.
- **Cooldown Configurável**: Ajuste o tempo de cooldown entre os teletransportes.
- **Partículas ao Teletransportar**: Exiba partículas durante o teletransporte. (opcional)
- **Persistência de Dados**: Armazena as homes dos jogadores em um banco de dados MySQL.
- **Partículas em trajetória**: Exibe partículas na trajetória do Wind Charge. (opcional)
- **Velocidade do Projétil**: Altera a velocidade do projétil Wind Charge.
- **Poder de Explosão**: Altera o tamanho da explosão ao contato do item Wind Charge.

## Requisitos

- **Minecraft**: Versão 1.21
- **Spigot**: Compatível com a versão do Minecraft (Neste caso 1.21)
- **Java**: 21 ou superior
- **MySQL**: Para armazenamento dos dados das homes
- **Gradle**: Para buildar o plugin

## Configuração

### Configuração do MySQL

Certifique-se de ter o MySQL instalado e configurado. Altere seus dados de conexão com banco de dados, especificado no arquivo de configuração.

### Configuração do Plugin

Edite o arquivo `config.yml` no diretório de configuração do plugin para rodar o projeto. Exemplo de configuração:

```yml
mysql:
  host: "localhost"
  port: 3306
  database: "minecraft"
  username: "root"
  password: sua_senha_mysql

windcharge:
  explosionStrength: 4.0
  spawnParticles: false
  projectileSpeed: 1.5

home:
  cooldown: 10
  teleportParticles: true
```

## Comandos

- `/sethome [nome]`: Define um local como uma home com o nome especificado.
- `/teleport [nome]`: Teletransporta o jogador para a home com o nome especificado.
- `/getitem`: Obtém 90 Wind Charges.
- `/setwindcharge explosionstrength [valor]`: Define a força da explosão do WindCharge.
- `/setwindcharge projectilespeed [valor]`: Define a velocidade do projétil Wind Charge.
- `/setwindcharge spawnparticles [true | false]`: Ativa ou desativa as partículas do projétil Wind Charge.
- `/teleportcd [tempo]`: Define o cooldown de teletransporte.
- `/teleportparticles`: Ativa ou desativa as partículas ao teletransportar.

## Estrutura

Para gerar um .jar do plugin:

1. Após abrir o projeto em sua IDE, altere os dados de conexão do banco de dados no arquivo `config.yml`, localizado na pasta `src/main/resources`. Pode alterar os valores das propriedades do Wind Charge e Home, respeitando o tipo definido. 
2. Após alterar os dados de conexão com banco de dados, abra o terminal, navegue pelo terminal até a pasta `gradle-build/plugin`, e digite o comando `gradle clean build -x test`. Este comando builda o projeto sem gerar os testes antes. É importante buildar sem os testes pois não os configurei.
3. Após o build, o plugin estará disponível na pasta `gradle-build/build/libs`. Copie o arquivo .jar gerado e cole na pasta `plugins` do seu servidor.
4. O servidor utilizado no plugin foi o Spiggot versão 1.21, localizado em https://getbukkit.org/get/4063d239ce16b22d948c037ce7a9fb8c.
5. Com o download da versão especificada e a posterior configuração do servidor, é necessário colar o plugin gerado na pasta "plugins" e rodar o servidor.
6. Com o servidor rodando, clique em multiplayer e conecte-se na porta "localhost".

