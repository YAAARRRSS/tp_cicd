###Etape1

--Nouveau Repo:

mkdir TP4
cd TP4
git init


--Génération clé SSH

ssh-keygen -t ed25519 -C "yann.bessou@ynov.com"
cat ~/.ssh/id_ed25519.pub

--Creation du repository github + ajout clé ssh publique

settings -> SSH  puis collé la clé


-- Liée à mon git locale:

git remote add origin git@github.com:YAAARRRSS/tp-cicd.git


--Tester un premier commit:

touch README.md
git add README.md
git commit -m "Initial commit"
git push -u origin git_rep

###Etape2

--Creer le dossier et fichier workflows:


mkdir -p .github/workflows
nano .github/workflows/ci.yml

-Collé le contenu du lien du TP:

https://docs.github.com/fr/actions/get-started/quickstart


###Etape3


---Python

Creation de simple_math.py

Puis de test_simple_math.py



###Etape4


--Modification du ci.yaml via github

-Il faut donc ensuite recuperer les changement qui ne sont pas en local:

git pull --rebase origin git_rep

-Puis un git commit:

git commit -m "CI: Ajout du run des tests unitaires Python"
git push


###Etape5

 
--Ajout de la fonction soustraction dans les fichiers : simple_math.py et test_simple_math:

def soustraction  



###Etape6

--Ajout du lint ou plylint dans le workflow

 - name: Install pylint
        run: pip install pylint


###Etape7

---Creation d'un dockerfile qui execute les tests


RUN pip install pytest



