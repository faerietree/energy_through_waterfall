EDUWAFA - Energie Durch WAsserFAll [Codename Wasserfall]


Energiegewinnung Wasser - Übersicht:
=================

Energie durch Wasserbewegung (EDUWABE) oder korrekter durch Impuls (EDUWASI) (Im Gegensatz zu Energie durch Ausnutzung der Wasserträgheit, was ich mir auch vorstellen könnte.)
Das wären: Zwischenfrage: Gibt es neben planar, vertikal und zirkulär (Vortex, Wirbel) weitere Typen?

* vertikal:
  * EDUWAFA (WAsserFAll - High head hydro power plant)
  * EDUWAMA (WAsserMAssen - Low head hydro power plant)
* planar:
  * EDUWAFL (WAsserFLuss - Waterwheel (Wasserrad) z.B. HydroCat, wenn dann schon mobil)
* zirkulär:
  * EDUWATU (-"- WAsserTUrbulenz)
  * EDUWARO (-"- WAsserROtation oder WAsserKReisel: EDUWAKR)



Attention: This project setup is experimental.


Leitspruch:
=======

Entwicklungsentscheidungen lassen oft bitteren Streit in Open source Projekten entflammen (siehe z.B. KiCAD), deshalb schon hier ein Leitspruch nachdem sich alle Entscheidungen richten:
*For the goals we bake, the best and simplest solutions we take.*
Notes:
* Goals is important. Not the simplest solution (which to just build nothing) we adopt. Instead the solution still must meet the goals. And thus it's the simplest possible solution to our knowledge so far. If new knowledge arises, and provides a simpler solution that fulfills the same goals, then this is adopted. Note that static solutions not count as simpler, because over course of time in static solutions, it's getting more and more difficult to keep track of the interconnections.
   
* Since simplicity in most cases implies low-cost and often reliability and easy maintenance, that is not explicitely stated. There may be exceptions where the simplest solution is more expensive.
* By using plural ('solutions') this short maxim also implies that we will not stick with one solution and are open to multiple solutions in several project branches.

  All is kept under a versioning system. Common files desirably are put in the highest level folder that is still under versioning. (So there is no extra 'common' folder - instead the highest project level automatically is common to all branches without naming it anywhere.)

  Using a Git submodules project in the highest level will provide all the required functionality for common solutions and exchanging links to the most advanced solution that has been developed.

  For sake of equality, there is nothing like a master-branch, each branch is an equal development effort.

  A branch is named after the category name and its technical/development approach/route it chose to pursue.
e.g. using this pattern:
    $PROJECT_DIRECTORY/<ordering_using_three_digits*_if_desired>-<Modul>-<how_it_s_done1>/<ordering_3digits*>-<submodule>-<how_it_s_done>/


\*3digits because this way it's easy to insert another entry/module inbetween some two other modules at all times. Though this numbering scheme may be omitted if loading order is not important (which depends on the project's software/hardware loading functionality).


###There are two possibilites:

* Every folder in the highest level of the project file structure is an individual repository. Each repository has its own branches for going a different development route or hot-fixing/further developing a previous release (while development of the red thread continues).
The main/highest level (wrapper/submodules-hybrid) project also may have branches, if opinion differs and a developer prefers a different linking or configuration or interaction of (sub-)modules.

OR


* We have only two major sub-repositories in the highest level:
  * `final`/`trunk` where there is no `-How:<how_it's_done>/` addition to the folder names.
  * `branch` where there is all development and each folder can be checked out and committed separately. (hence the highest level project here will turn into a recursive submodules project)
In this approach checkout and changes are more refined and thus there is less overhead. I think this is not worth it.


* In the highest level repository the links/submodule URI entries may or may not omit the `-How:<how_it's_done>`. As the highest level submodule configuration is a complex solution interlinking different independent (sub-)modules, its goal is to provide real world solutions out of all available components/(sub)modules.

*Note: It can't be guarantueed that every branch will reach a state where it'll resemble a working real life situation. But it should have it as goal, non-working concepts won't be deleted but activity will just be non-existent. This will save hassle and quarrels among developers (because who shall decide what is going to be deleted and what not).

If a branch is deleted, then the contributors must do this themselves in union without any veto and furthermore give a reason (as always when removing/adding/modifying things, especially and foremost when operating on code/designs of other people).

If the branches are listed from most active to least active, this would filter non-working/non-progressing solutions automatically. It would also show which repository branch is most promising or simplistic (because highest pace may be expected with simple solutions). Note our maxim above states a solution must still fulfill our requirements/goals.*

The chosen development folders also may be linked into these main folders using symbolic links.


The most mature submodules can simply be linked in a wild mix as long as those sub/modules are disjunct and that mostly is the case. Mixed not is meant as intermangled into each other though, which should be handled by Git merge instead. Mix means mix the repo's respective highest level folders (all as links to avoid redundancy).

Through this freedom, way even the review can be omitted and every new idea will simply get its own folder (better: branch) in which we note what is special about this solution (e.g. via the `How:<how_it's_done>/` in the folder name).

*Note: This last approach is similar to the first. This and the first could be combined into one.*


The submodules repositories within the highest level repository must not necessary be checked out at once (see Git documentation). Instead only the repos a developer is interested in, can be checked out.

As said before, the highest level 'best solution' (containing mostly linked folders/ submodule repository URI entries and common files) needn't be used locally. If one does not like the choices, one can always link differently on the local machine (not forget to create a new branch in the highest level repository such that the modules choices/configuration can be shared and evaluated).






###Example for Possibility 3 (see list above):

*(If numbering is optional or not depends on if a certain loading sequence is required. Same folder base means these are branches. The `-How:<how_it's_done>` symbolises which branch is meant/checked out.)*

    Energy_Hydro_EDUWAFA/
    / \
        010-Power-How:nuclear_and_fuel_cells/
            010-Nuclear-How:Cold_fusion/ ...
            010-Nuclear-How:Hot_fusion/ ...
            020-Fuel_cell-How:only_using_water_as_electrolyt/ ...
            020-Fuel_cell-How:I'm_convinced_this_is_simpler/ ...
        010-Power-How:fuel_cells_only/
            010-Fuel_cell-How:air_cathode_choke/ ...
        015-Gravity_wheel-added_this_inbetween_Power_and_Hull/
            - no sub directories yet -
        020-Hull-How:I'm_convinced_this_interaction_of_electronics_and_mechanics_is_better/
            010-Mechanics-How:using_titanium_micro_meteor_shield/ ...
        020-Hull-How:but_I'm_convinced_the_mechanics_don't_need_to_have_those_electronics_hooks_if_we_glue_them_to_the_walls_instead/
            010-Mechanics-How:using_titanium_micro_meteor_shield/ ...
            020-Electronics-How:never_using_bolts_instead_glue_all/ ...
            020-Electronics-How:good_idea_but_no_I_prefer_keeping_thebolts_and_using_the_glue_additionally/ ...





###Entwicklungsentscheidungen - Beispiel:

    As an example for how to come to a solution, for the question if we merge some patch or not, consider we want to achieve the following:

    Our batteries must not break (e.g. catch fire). Implies: Have a reasonable long lifetime.

*This goal is subsequently called a requirement interchangably.*

So we choose long-life batteries (current state of the art is LiFePO4 which is heavily tested and used by the military, recently bad light was shed on the batteries due to Airbus battery problems).

    Fulfill the most essential/minimalistic yet goal-fulfilling modules' peak energy demand.

*Note: The general rule is to never be destructive, e.g. don't trade a module's health for others if it can be avoided not required, e.g. in emergency situation, or the alternative or a consequence of it is worse.*


Of the below solution would be worthless without context like environment/setting/location, e.g. in space or not, from which conditions, and must be interlinked all back to a single source.


We need batteries for full-filling peak energy demand (e.g. switching on strong electric motors where we require a lot of 'invisible' power). If we omitted them, what is possible, we had to switch to grid-power whenever a high energy demand was required. In cases where there is an electric power grid available this is an option.


 As these high-power-demand peaks don't occur too often, a very small capacity battery will do - as a starting point we use 10 Ah for supplying 10A for one hour or 20A for half an hour (and so on). As we talk of three phase power what is usually required for farmers (and open source ecology needs to build farms for foraging any kind of food in an ecological way). So we talk of 700V DC batteries here. That means that roughly 20A * 410V = 8200 W peak power can be supplied for half an hour. If the water plant runs short of water or fails out of another reason, this of course probably is not enough time to repair the hydro power plant, but the best way to realize that something is wrong with the plant is that there is no more electricity anyway (unless some critical applications are running, so the 30 minutes give enough time to either deploy an emergency generator or get the job done or terminate the ciritcal electric machine in a soft way instead of the hard and sudden stop of electric energy supply.).

    How?
        Batteries must not be overcharged.
        Batteries must not be drained fully empty.
        Batteries must not be unbalanced. (Special for Lithium type batteries, on he other hand they don't suffer from memory effect like Nickel batteries do and have a much longer mean lifetime.)
    Now to fulfill this we deployed a very strange and unconventional strategy and I know that people will complain about heavily. Nevertheless I will test this approach because it is the simplest yet best solution, because it still fulfills all the requirements for keeping the batteries healthy.

    If now of course another developer makes another proposition this will immediately and automatically result in creating a branch for the developer's idea. There are no people that have the power to stop this idea, we don't have hierarchies (at least for projects that are under my command .. ha, funny Antithetik .. I meant those that I am part of).

    Once the simplest solution so far fails, we immediately can exchange trunk and the next simple and promising branch. This way noone will be angry because some developer denies to give merge-permission in the patch merge-review. There are no patches that change the principle of how to do things unless they are simpler and still fulfill the requirements. Then the current solution gets into a new branch and developers that think this approach is most promising can still continue their efforts until they make the way back to trunk eventually by simplification and or breakthroughs that convince all the other developers.

    It's also good to discuss a new solution in a thread pior to implementing it as other developers could give some insights in how such a solution could be implemented (such to save the other developer some work and time).






EDUWAFA Ziel:
-----

* Elektrische Energieerzeugung: 2..20 kW (micro hydro).

  Der Prototyp konkret:
        Dual Output: 1x 2 kW bei Niedrigwasser (Sommer) + 1x 4 kW sonst.



Development:
-----

* BMS - BatterieManagementSystem *at least one solution is designed*. To be evaluated.
* Rohrleitung, bis dato wurde vergeblich nach gebrauchten und günstigen 10cm-Durchmesserrohren gesucht. Aber egal ob man Weinbauer fragte oder das Internet durchsuchte, immer gab es Probleme. Die ostdeutschen Länder waren zu weit entfernt oder die gefundenen Rohre hatten Bewässerungslöcher. 
 Natürlich, man könnte mehrere 5cm-Durchmesserrohre an Stelle des einen 10cm-Rohres verwenden. Komplexität stiege dadurch an, da mehrere Anschlüsse benötigt. Und mehrere Rohre entschlammt werden müssen. Unter anderem.


