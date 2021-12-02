print("------------------QUIZ-----------------------")
print("Será que você está sofrendo ou já sofreu cyberbullying?")
print("-=" * 23)


def jogo_QUIZ():
    suposições_alternativas = []
    suposição_correta = []
    questoes = 1

    for iniciar in questions:
        print("-------------------------")
        print(iniciar)
        for i in options[questoes - 1]:
            print(i)
        suposição_questions = input("Escolha (A, B, C, D ou E): ")
        suposição_questions = suposição_questions.upper()
        suposições_alternativas.append(suposição_questions)

        suposição_correta.append(verificação_resposta(questions.get(iniciar), suposição_questions, questoes))
        questoes += 1

    pontuação(suposição_correta, suposições_alternativas)


# -------------------------
def verificação_resposta(resposta, guessuposição_questionss, id):
    if resposta == guessuposição_questionss:
        print("CORRETO!")
        return 1
    else:
        print(justificativas[id - 1])
        return 0


# -------------------------
def pontuação(suposição_correta, suposições_alternativas):
    print("-------------------------")
    print("RESULTADO")
    print("-------------------------")

    print("Respostas: ", end="")
    for i in questions:
        print(questions.get(i), end=" ")
    print()

    print("Suas respostas: ", end="")
    for i in suposições_alternativas:
        print(i, end=" ")
    print()
    score = 0
    for i in range(len(suposição_correta)):
        if suposição_correta[i] == 1:
            score += pontuacao[i]
    print("Sua pontuação é de: " + str(score))


# -------------------------
def jogar():
    resposta = input("Você quer jogar de novo? (Sim ou Não): ").upper()
    resposta = resposta.upper()

    if resposta == "SIM":
        return True
    else:
        return False


# -------------------------


questions = {
    "O que é um cyberbullying?: ": "C",
    "Um colega de classe te соntа quе еѕtá triste, роіѕ еѕtãо lhе оfеndеndо соnѕtаntеmеntе nаquеlа аulа оu еnсоntrо tãо lеgаl оnlіnе. Соmо vосê роdе ајudá-lо?: ": "A",
    "Como impedimos o cyberbullying sem desistir do acesso à internet? ": "C",
    "Como eu evito que minhas informações pessoais sejam utilizadas para me manipular ou me humilhar nas mídias sociais? ": "D",
    "Existem ferramentas online contra o bullying para crianças, adolescentes ou jovens? ": 'D',
    "Quais são os efeitos do cyberbullying?": 'A',
    " Qual a diferença entre uma brincadeira normal e bullying virtual?": 'C',
    "A que ponto o Cyberbullying passa a ser crime?": 'E',
    "Como identificar o comportamento de uma vítima de bullying?": 'B',
    "O que é pior: o bullying com agressão física ou o bullying com agressão moral?": 'A',
    ":O Ciberbullying ocorre em que segmentos da sociedade?": 'A',
    "Como lidar com o bullying contra alunos com deficiência? ": 'C',
    "Quais atitudes você deve ter para evitar que seja vítima de cyberbullying?": 'E'
}

justificativas = [["Resposta incorreta! O cyberbullying acontece da mesma forma que o bullying, com a única diferença que acontece online ou através de uso de telefones celulares ou dispositivos conectados."],
                  ["Resposta incorreta! O melhor caminho a ser fazer e aconselhando para que ele conte aos pais dele, pois eles saberão como agir."],
                  ["Resposta incorreta!  A união entre família e leis de proteção ao usuário na internet, assim estimulando mais pessoas a navegarem com segurança na internet."],
                  ["Resposta incorreta! Limitando ao máximo o número de pessoas que tem acesso a sua conta, restringindo-a para pessoas de confiança, e tendo cautela do conteúdo postado, para não ser nada muito pessoas ou chamativo."],
                  ["Resposta incorreta! Sim, existem ferramentas que restrijem que pessoas comentem e vejam seu perfil e suas publicações."],
                  ["Resposta incorreta! Os efeitos causado do cyberbullying em uma pessoa podem deixar marcas mentalmente, emocionalmente ou fisicamente."],
                  ["Resposta incorreta! A principal diferença se da pelo mantimento na qual na brincadeira ambos os lados se divertem e o cyberbullying se dá apenas por um lado."],
                  ["Resposta incorreta! A vitima sendo afetada pelos crimes contra a honra ou até injuria racial sem a autorização, estara sendo resguardada pelo artigo 138 e 140 do código penal brasileiro."],
                  ["Resposta incorreta!  O comportamento se dá pelo ato da vitima ter mais dificuldades de se impor, se afastando de quase todos seus bens."],
                  ["Resposta incorreta! Ambas são agressoes graves que podem causar danos a vitima."],
                  ["Resposta incorreta!  Pode ocorrer em qualquer local, sendo executadas em uma relação desigual de poder."],
                  ["Resposta incorreta! Conversar abertamente sobre a deficiência no cotidiano"],
                  ["Resposta incorreta! Evitar a exposição de intimidades na internet."]]

pontuacao = [5, 5, 5, 5, 5, 8, 8, 8, 8, 8, 15, 15, 15]

options = [["A. Não tem nada a ver com bullying",
            "B. É um estudo de jogos online",
            "C. É a mesma coisa que bullying, , com a única diferença que acontece online ou através de uso de telefones celulares ou dispositivos conectados.",
            "D. É uma brincadeira feita entre amigos",
            "E. Um site que explica o bullying"],
           ["A. Aconselhando para que ele conte aos pais dele, pois eles saberão como agir",
            "B. Dizendo pra ele partir pra briga física", "C. Não saberia como ajudar",
            "D. O ajudando no próximo encontro online a ofender essa pessoa",
            "E. Dizendo para ele ofender também essa pessoa "],
           ["A. O governo acabar criando uma legislação inteira, dedicada a crimes de ódio em ambiente digital.",
            "B. Não fazer nada, pois o cyberbullying é dever da família e do próprio individuo em procurar ajuda.",
            "C. Conscientizar toda a população sobre os perigos do cyberbullying, e como só acontece no ambiente virtual, não tendo nenhuma consequência na vida fora da internet. ",
            "D. Prender automaticamente todos que tiveram qualquer envolvimento com algum tipo de discurso de ódio em ambiente digital. ",
            "E. A união entre família e leis de proteção ao usuário na internet, assim estimulando mais pessoas a navegarem com segurança na internet."],
           ["A. Não temos como evitar esse fato, pois quando aceitamos participar de uma rede social queremos que nossos dados pessoas sejam vistos e usados por outros indivíduos.",
            "B. Não entrando em nenhuma rede social, quando se cria uma rede social você já aceitou que suas informações pessoas sejam vistas e aproveitadas por terceiros. ",
            "C. Não aceitar qualquer utilização de informações suas contra a sua vontade, tomar medidas legais e jurídicas contra quem fazer isso.",
            "D.  Limitando ao máximo o número de pessoas que tem acesso a sua conta, restringindo-a para pessoas de confiança, e tendo cautela do conteúdo postado, para não ser nada muito pessoas ou chamativo. ",
            "E. Nenhuma das alternativas anteriores"],
           ["A. Não. ",
            "B. Existem! Mas se tem uma taxa de segurança a ser paga",
            "C. Estudos apontam que essas ferramentas não ajudam em nada, por isso nao existe",
            "D.  Sim, existem ferramentas que restrijem que pessoas comentem e vejam seu perfil e suas publicações.",
            "E. Existem, mas nao funcionam. "],
           ["A. Os efeitos causado do cyberbullying em uma pessoa podem deixar marcas mentalmente, emocionalmente ou fisicamente.",
            "B.  Não há efeitos, pois é feito pela internet e isso não causara nada ao ser humano que esteja passando por isso.",
            "C. Só causam efeitos em  algumas pessoas",
            "D. Sendo apenas uma brincadeira nao irá causar danos de nenhum modo.",
            "E. Só causara danos em adolescentes ate os 19 anos."],
           ["A. Ambas são brincadeiras, a unica diferença se da pelo lado virtual e a outra na realidade.",
            "B. Não existe diferença.",
            "C.  A principal diferença se da pelo mantimento na qual na brincadeira ambos os lados se divertem e o cyberbullying se dá apenas por um lado se divertindo, ou seja, o do agressor.",
            "D. Ambas sao iguais.", "E. As duas são apenas brincadeiras sadias, so que uma é virtual."],
           ["A. O cyberbulliying não chega a ser um crime.",
            "B. Estudos dizem que nao é crime, apenas uma brincadeira online",
            "C. É um crime sério, com risco de prisão perpétua. ",
            "D. O cyberbullying é apenas um jogo, de forma que não entra nos paramentros de crime.",
            "E. A vitima sendo afetada pelos crimes contra a honra ou até injuria racial sem a autorização, estara sendo resguardada pelo artigo 138 e 140 do código penal brasileiro."],
           ["A. O comportamento é sociavel e o mais extrovertido possivel, sempre se sercando de muitas pessoas",
            "B. O comportamento se dá pelo ato da vitima ter mais dificuldades de se impor, se afastando de quase todos seus bens.",
            "C. Não tem como identificar uma pessoa que esteja sendo vitima de cyberbullying.",
            "D. A pessoa que foi vítima de bullying dificilmente terá algum problema de socialização.",
            "E. O indivíduo que tem sofrido bullying ele acaba ficando mais introvertido, porém nada que prejudique a sua habilidade de socialização"],
           ["A. Ambas são agressoes graves que podem causar danos a vitima.",
            "B. Ambas são brincadeiras legais na qual ha entreterimento de diverção para todos os lados.",
            "C. Nenhuma causa danos.",
            "D. A agressão física é pior, pois a agressão moral não tem o efeito de ferir o indivíduo fisicamente.",
            "E. A agressão moral é pior, já que agressões físicas se curam com o tempo, porém isso não ocorre com o psicológico da vitima."],
           ["A. Pode ocorrer em qualquer local, sendo executadas em uma relação desigual de poder.",
            "B. Não ocorre em todos os segmentos da sociedade, apenas em âmbitos escolares.",
            "C. O Cyberbullying acontece principalmente no trabalho e estágios.",
            "D. Pode ocorrer em qualquer local, com seu alvo principal em idosos.",
            "E. Ocorre principalmente no segmento econômico."],
           ["A. Não ficar falando sobre a deficiente no cotidiano.",
            "B. Responder os insultos de volta, dizendo que está com raiva.",
            "C.  Insultar abertamente os alunos praticantes.",
            "D. Conversar abertamente sobre a deficiência no cotidiano", "E. Desligar o dispositivo e não fazer nada."],
           ["A. Nunca usar rede social, ser totalmente independente da internet",
            "B. Deixar seu perfil aberto para que qualquer um possa ver", "C. Bloquear comentários  ofensivos.",
            "D. Ser uma pessoa mais ativa nas redes sociais.", "E. Evitar a exposição de intimidades na internet."]]

jogo_QUIZ()

while jogar():
    jogo_QUIZ()

print("FIM!")
