# Exercice 1

1. Prédicat :
   - Rodolphe x Jean
   - relation : Cheval/1, lapin/1, levrier/1, chien/1
2.  
   cheval(Rod) 
   lapin(Jeannot)
   $\forall x \forall y \text{ cheval(x)} \land \text{ cheval(y)} \to \text{pr}(x,y)$
   $\forall x \text{ levrier(x)} \to \text{ chien(x)}$
   $\exists x \text{ levrier(x)} \land \forall y (\text{ lapin(y)} \to \text{pr}(x,y))$
   
   __Faits__:
   (1) cheval(Rod)
   (2) lapin(Jean)
   (3) levrier(lev)
   
   __Règles__:
   (4) $\text{cheval(x)}\land \text{ chien(y)} \to \text{pr}(x,y)$
   (5) $\text{levrier(x)} \to \text{ chient(x)}$
   (6) $\text{lapin(y)}\to \text{pr}(\text{Lev},y)$
   
   __Chaînage avant__ :
   $3, 5 \to (7) \text{ chien(lev)}$
   $1,7,4\to(8) ~~\text{pr}(\text{Rod}, \text{lev})$
   $2,6 \to (9) ~~\text{pr}(\text{lev}, \text{Jean})$
   
   __Transformation en clause__ :
   
   (1) cheval(Rod)
   (2) lapin(Jean)
   (3) levrier(lev)
   (4) $\lnot \text{cheval(x)} \lor \lnot \text{chien(y)}\lor \text{pr}(x,y)$
   (5) $\lnot\text{levrier(x)} \lor \text{chien(x)}$
   (6) $\lnot\text{lapin}(y)\lor \text{pr(lev,y)}$
   (7) $\lnot\text{pr(x,y)}\lor \lnot\text{pr(y,z)}\lor \text{pr(x,y)}$
   