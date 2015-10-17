# ex4-fiche-tp1
package exo4;

/**
 * Created by Princess Of Persia on 17/10/2015.
 */
public class De {

    public int Tirer(){
        return ((int)((Math.random() * 6) + 1));
    }

   /* public static void main(String[] args) {
        De t = new De();

        for (int i = 0; i < 7; i++) {
            System.out.println(" "+t.Tirer());
        }
    }*/
}


public class Joueur {
    /*String Nom;

    public Joueur() {
        this.Nom = null;
    }

    public Joueur(String nom) {
        Nom = nom;
    }*/


    De t = new De();
    public int Score(int J){
        //int s = J;
        //int c = t.Tirer();
        //System.out.println("tirer  "+c);
        J = J + t.Tirer();
        return J;
    }

    //public static void main(String[] args) {
    //  Joueur J = new Joueur();
    //  int s = 0;
    //  Joueur j = new Joueur("Sarah");
    //  for (int i = 0; i < 10; i++) {

    //    System.out.println(" "+J.Score(s));
    //    }
    //}*/
}



import java.util.Scanner;

/**
 * Created by Princess Of Persia on 17/10/2015.
 */
public class GameOn {


    public static void main(String[] args) {

        Scanner scan = new Scanner(System.in);
        System.out.print("donner le nombre de joueurs !\t");
        int n = scan.nextInt();
        Joueur[] joueurs = new Joueur[n];
        int [] element = new int[n];

        Joueur J = new Joueur();
        //De d = new De();
        // creatio de la liste de joueurs
        //for (int i = 0; i < n; i++) {
            //System.out.print("donner le nom stp\t");
            //joueurs[i] = new Joueur(scan.next());
            //System.out.println(joueurs[i]);
        //}
        //affichage des noms de joueurs
        //*for (int i = 0; i < n; i++) {
        //    System.out.println("le joueurs N "+(i+1)+" est "+joueurs[i]);

        //}*/

        System.out.println("************** Jeu De Des **************");
        System.out.println("1-   Nombre De Joueurs "+n+"\n");
        int c = 2;
        for (int i = 0; i <  10; i++) {
            System.out.println(c+"-  Tour n  "+(i+1)+"\n");
            c++;
            for (int j = 0; j <  n; j++) {
                element[j] = J.Score(element[j]);
                System.out.println(c+"-  Joueur"+(j+1)+" a "+element[j]+"\n");
                c++;
            }
        }
        int max = element[0];
        int indice = 0;
        for (int i = 1; i < n ; i++) {
            if (element[i] > element[i-1]) {
                max = element[i];
                indice = i;
            }
        }
        System.out.println(c+"-  Le Gagnant Est Le Joueur"+(indice+1)+" avec le score de : "+max+" points");
    }
}
