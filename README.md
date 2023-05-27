# solar-irradiance-prediction
**Task:** optimize solar power production by building a model which accurately predicts irradiance using some data.
# Problem It Solves
After witnessing harmful effect of fossil fuels on our enviornment and realising it's exhaustability we are trying to make advancement in renewble clean energy sources.Solar energy energy being one of them is harnessed using solar plates whose orientation along with weather conditions determine how much electricity will be generated.
This challenge attempts to predict solar irradiance components which will help solar power generation company in maximizing it's electricity generation through proper solar panel orientation.With this we step towards cleaner,non exhaustible energy sources.

 # Challenges along the way
During the course of the project,a few challenges were faced.Some of the challenges are listed below:-
* **Correlated targets :** First challenge was to figure out way to do multitarget prediction as we had to predict DNI irradiance, DHI irradiance and GHI irradiance all while them being affecting each other.So naive method was just to predict them separately but this had poor performance.Then I came up with a very effective method in which one predicted target was included in train data of other target.
* * hh
* 
