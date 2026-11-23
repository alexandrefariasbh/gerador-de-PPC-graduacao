# Gerador de PPC para Cursos de Graduação

Este é um gerador de Projeto Pedagógico de Curso (PPC) para os cursos de graduação da Universidade Federal de Ciência e Inovação de Minas Gerais (UFCIMG), o antigo CEFET-MG. Nesta primeira versão, ele atende aos cursos de Engenharia.

A ideia deste gerador é que as coordenações de curso e os Núcleos Docentes Estruturantes produzam PPCs institucionais padronizados, todos no mesmo formato: o modelo da Instrução Normativa DIRGRAD nº 01/2023, com os mesmos quadros, carga horária dentro das normas, disciplinas equalizadas conforme as resoluções do Conselho de Graduação e referências em ABNT. A coordenação preenche o conteúdo, e o documento sai pronto, no padrão institucional.

## Como funciona

O gerador abre direto no navegador, sem instalar nada e sem login. Funciona nas versões atuais do Chrome, Edge, Firefox e Safari.

Ao abrir, ele começa em branco. Em **Novo**, você escolhe começar em branco, importar o PPC vigente do curso ou partir de um PPC existente. Depois, segue as etapas do menu lateral:

1. **Identificação e capa:** curso, campus, turno, vagas, integralização, dirigentes, comissão, NDE e colegiado.
2. **Textos do projeto:** as seções 1 a 7 do modelo da IN DIRGRAD nº 01/2023, com orientação em cada uma e contador de caracteres (máximo de 8.000 por seção).
3. **Competências do egresso:** as competências C1, C2… da DCN das engenharias. Um botão inclui as oito competências gerais do art. 4º da Resolução CNE/CES nº 2/2019.
4. **Eixos de conteúdos:** nome, objetivos, competências e ementa de cada eixo.
5. **Disciplinas:** eixo, período, horas-aula teóricas e práticas, área de formação da DCN, característica, competências, pré e correquisitos, ementa e bibliografia.
6. **Matriz curricular visual:** o curso em fluxograma, período a período, para avaliar e remanejar as disciplinas.
7. **Atividades e carga horária:** optativas, eletivas, atividades complementares, extensão, Projeto Final de Curso e estágio.
8. **Pessoal docente e NDE:** professores e composição do Núcleo Docente Estruturante.
9. **Pendências:** a conferência automática de todo o projeto.
10. **Gerar documentos:** o PPC pronto em PDF ou .docx.

## Importar o PPC vigente e reestruturar

O botão **Importar PPC** (ou **Novo → Importar o PPC vigente do curso**) lê um PPC de graduação já pronto, em PDF ou Word (.docx), no formato da IN DIRGRAD nº 01/2023. O gerador aproveita:

- a ficha de identificação do curso;
- as comissões, o NDE, o colegiado e a lista de siglas;
- os textos de todas as seções;
- as competências do egresso;
- os eixos do Quadro 1, com objetivos, competências e ementas;
- as disciplinas do Quadro 2, com eixo, período, carga horária, característica, área de formação, competências, pré e correquisitos e ementa;
- a carga horária das atividades do Quadro 3;
- a bibliografia do Apêndice I.

Antes de usar, o gerador mostra um resumo do que leu. Depois, é só editar o que muda na reestruturação e gerar o PPC novo. O PPC lido fica guardado como **PPC anterior**, para referência. PDFs digitalizados (imagem) não têm texto para ler; nesse caso, use o .docx.

## Matriz curricular visual

A matriz mostra o curso como um fluxograma, no formato usado pelos colegiados: uma coluna por período, com a carga horária do semestre e a acumulada. Cada cartão traz o código da disciplina, a carga horária, o número sequencial e os pré e correquisitos.

- **Clique em um cartão** para ver todos os detalhes da disciplina num painel lateral e editá-la ali mesmo. As disciplinas equalizadas (🔒) aparecem só para leitura: nome, ementa, carga horária, pré e correquisitos e bibliografia seguem a resolução.
- **Arraste um cartão** para outro período (ou para as optativas) para remanejar. As cargas horárias se atualizam na hora.
- Ao passar o mouse, os pré-requisitos ficam em azul, os correquisitos em verde e as disciplinas que dependem dela em laranja. Conflitos aparecem em vermelho.
- Em **Atividades por período**, você indica onde entram as ações de extensão (AEx), as optativas, o estágio e o Projeto Final de Curso.
- Você escolhe as cores (por eixo, área de formação, característica ou natureza), a unidade (horas ou horas-aula) e como os pré-requisitos são indicados (número sequencial ou código).
- O quadro-resumo traz os componentes curriculares, a carga horária total e a data de aprovação pelo colegiado.
- **Imprimir / salvar em PDF** gera a matriz em folha A3 deitada.

## Trabalho em equipe (edição simultânea)

Vários professores podem trabalhar no mesmo PPC ao mesmo tempo. Cada alteração aparece para os outros em poucos segundos.

1. Clique em **Equipe** e entre com a sua **conta Google pessoal** (por exemplo, @gmail.com). Quem não tem conta Google pode entrar com qualquer e-mail pessoal e uma senha criada só para o gerador, confirmando pelo link que chega no e-mail. Não é preciso usar o e-mail institucional.
2. Com o PPC aberto, clique em **Compartilhar este PPC**. Ele passa a ficar guardado na nuvem.
3. Convide os colegas pelo e-mail que eles usam para entrar (o Gmail, por exemplo) e envie a eles o **link do PPC**. Quem abre o link e entra com o e-mail convidado cai direto no PPC. Quem não foi convidado não consegue abrir.
4. Em **Equipe**, você vê quem é membro e quem está on-line. No cabeçalho aparecem as iniciais de quem está on-line; no menu lateral e na lista de disciplinas, as iniciais mostram onde cada pessoa está editando.

As alterações são gravadas campo a campo. Duas pessoas editando campos diferentes (a ementa de uma disciplina e a bibliografia de outra, por exemplo) não se atrapalham. Se duas pessoas mudarem o mesmo campo ao mesmo tempo, vale a última alteração, e o gerador avisa quando há outra pessoa na mesma tela. **Salvar**, **Abrir** e **Gerar documentos** continuam funcionando normalmente, e **Salvar** é uma boa forma de guardar uma cópia de segurança.

### Como ativar (feito uma vez, por quem administra o gerador)

A edição em equipe usa o Firebase Realtime Database, do Google, no plano gratuito (Spark), que não pede cartão.

1. Em https://console.firebase.google.com, crie um projeto (por exemplo, `gerador-ppc-ufcimg`). O Google Analytics pode ficar desligado.
2. Em **Criação → Realtime Database**, crie o banco no **modo bloqueado**. Na aba **Regras**, apague o conteúdo, cole o do arquivo `firebase-regras.json` deste repositório e clique em **Publicar**.
3. Em **Authentication → Método de login**, ative o **Google** e, para quem não tem conta Google, **E-mail/senha** (só a primeira chave; o “link do e-mail” fica desligado).
4. Em **Authentication → Configurações → Domínios autorizados**, adicione `alexandrefariasbh.github.io`.
5. Em **Configurações do projeto → Seus apps**, adicione um app **Web** (`</>`) e copie o bloco `firebaseConfig`.
6. No repositório, crie o arquivo `colab.json` a partir de `colab.exemplo.json`, preenchendo com os valores copiados. Confira se o `databaseURL` está lá; ele aparece no topo da página do Realtime Database.

O `colab.json` não é uma senha: ele só diz ao gerador qual projeto usar. Quem controla o acesso são as regras publicadas no passo 2: só membros convidados leem e alteram cada PPC. Se um dia quiser restringir a um domínio de e-mail, informe-o em `dominios` no `colab.json`.

## O que o gerador monta sozinho

A partir dos eixos, das disciplinas e das atividades, o gerador monta todos os quadros do modelo:

- **Quadro 1:** eixos de conteúdos e atividades, com o desdobramento em disciplinas e atividades;
- **Quadro 2:** apresentação de cada disciplina;
- **Quadro 3:** síntese da distribuição da carga horária, com os percentuais;
- **Quadro 4:** carga horária obrigatória por eixo;
- **Quadro 5:** disciplinas optativas;
- **Quadro 6:** disciplinas por período, com carga semestral e acumulada;
- **Quadro 7:** matriz curricular em fluxograma, numa folha deitada, no modelo da IN: cada disciplina num cartão com código, carga horária, número e pré e correquisitos, nas cores dos eixos, com as atividades (extensão, optativas, estágio e PFC) nos períodos indicados;
- **Quadro 8:** relação entre as competências do egresso e as disciplinas;
- **Apêndice I:** bibliografia por disciplina.

A numeração das disciplinas é automática, no formato da IN (01/1) ou no formato período.ordem/eixo (1.01/1). A carga horária em horas é calculada a partir das horas-aula de 50 minutos.

## Disciplinas equalizadas

Em **Disciplinas**, o botão **+ equalizada** abre o catálogo das disciplinas equalizadas das Resoluções CGRAD nº 05, 06, 07, 08, 09 e 14/2022 (Computação, Matemática, Física, Química e Humanidades e Ciências Sociais Aplicadas). Ao incluir uma disciplina, o gerador preenche a ementa, a carga horária, o período estimado e a bibliografia da Deliberação CGRAD nº 32/22 (campi Nova Suíça e Nova Gameleira), e liga os pré e correquisitos às disciplinas que já estão no projeto. Se a ementa ou a carga horária de uma equalizada for alterada, o gerador avisa.

## O que o gerador confere

Enquanto você preenche, o gerador confere o projeto contra a IN DIRGRAD nº 01/2023 e nº 02/2023, a Resolução CEPE nº 18/22, a DCN das engenharias e a Resolução CNE/CES nº 7/2018. Ele avisa, por exemplo, quando:

- a carga horária total não chega a 3.600 horas;
- a extensão não alcança 10% da carga horária total;
- o estágio tem menos de 160 horas;
- uma seção passa de 8.000 caracteres;
- uma disciplina não tem 3 títulos de bibliografia básica e 5 de complementar;
- um pré-requisito não está em período anterior;
- algum conteúdo básico obrigatório da DCN não aparece nas disciplinas;
- uma competência não é desenvolvida por nenhuma disciplina.

Cada aviso tem um atalho que leva direto ao campo a ser corrigido. A norma citada no aviso também é clicável: o gerador abre o documento (IN DIRGRAD, resolução do CGRAD ou deliberação) na página do trecho correspondente, com o trecho destacado em amarelo. As leis e resoluções federais abrem no site oficial.

O limite de 8.000 caracteres por seção vem do modelo de PPC da IN DIRGRAD nº 01/2023 (Anexo II), que indica “Máximo de caracteres: 8000” em cada seção. A própria IN diz que esse limite é sugerido, para manter o texto objetivo. Por isso, passar do limite gera um aviso, e não uma pendência.

## Recursos

- **A partir de PPC existente:** em **Novo**, você pode abrir o PPC de Engenharia de Materiais (Campus Nova Suíça, 2022) para se orientar, e editá-lo e adaptá-lo ao seu curso. Ele vem sem nomes de pessoas.
- **Prévia do PPC:** mostra o documento sendo montado ao lado do formulário, atualizado enquanto você digita.
- **Normas e documentos:** reúne as Instruções Normativas DIRGRAD nº 01/2023, 02/2023 e 06/2026, as Resoluções CGRAD das disciplinas equalizadas (nº 05, 06, 07, 08, 09 e 14/2022), a Deliberação CGRAD nº 32/22 e os links da legislação.
- **Sobre este gerador:** este texto, com o passo a passo de uso.
- **Compartilhar o gerador de PPC:** copia o link do gerador para enviar a colegas.

## Onde ficam os dados

Tudo o que você digita fica salvo apenas no seu navegador. Nada é enviado para servidores, a não ser os PPCs que você compartilhar em **Equipe**, que ficam no Firebase com acesso restrito aos convidados. Por isso:

- para continuar em outro computador, ou passar o projeto a um colega, use **Salvar**. Ele gera um arquivo no seu computador, que depois pode ser aberto em **Abrir**;
- se você limpar os dados do navegador, o rascunho se perde, então salve o projeto com frequência;
- ao reabrir o gerador, ele começa em branco e oferece **Continuar rascunho** caso haja trabalho anterior salvo naquele navegador.

## Versão

A versão aparece no topo da tela, ao lado do título. Se o navegador continuar mostrando uma versão antiga, recarregue a página (Ctrl+Shift+R no Windows, Cmd+Shift+R no Mac).

## Arquivos deste repositório

- **`index.html`**: o gerador completo, em um único arquivo. É o que o GitHub Pages publica.
- **`README.md`**: este texto.
- **`colab.json`**: a configuração da edição em equipe (criada a partir de `colab.exemplo.json`). Sem ele, o gerador funciona normalmente, só que sem a edição em equipe.
- **`firebase-regras.json`**: as regras de acesso que vão no Firebase.

O `index.html` também funciona sozinho: baixe o arquivo e abra com dois cliques, mesmo sem internet.

## Sugestões e problemas

Sugestões, correções e relatos de problemas são bem-vindos. Abra uma *issue* aqui no GitHub ou fale diretamente com o autor.

## Autoria

Desenvolvido pelo Prof. Alexandre Rodrigues Farias, do Departamento de Eletrônica e Biomédica da UFCIMG.

LinkedIn: https://www.linkedin.com/in/alexandre-rodrigues-farias
