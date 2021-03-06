<p align="center">
  <img width="360" height="200" src="https://github.com/ULStats/MA4128Assessment-2018/blob/master/Kitman%20Labs/Images/Kitman%20Labs%20Logo.png">
</p>

__Kitman Labs__ 
===========================
:stuck_out_tongue_winking_eye:***Máire Condon**    13142259*


## Background
Stephen Smith founded sports technology company Kitman Labs in 2012 to enable professional and elite sports teams to help reduce injury risk and increase player availability. Prior to founding Kitman Labs, Stephen was senior injury rehabilitation and conditioning coach with Leinster Rugby for six years. Kitman Labs was founded in Dublin in October 2012, where its headquarters remain. The foundation of the company was Smith's Master's research, which focused on combined risk factors as predictors of athletic injury. 

Built by sports practitioners and data and sport scientists, Kitman Labs understands there is a better way to leverage the data available to sports coaches and staff. Based around its Athlete Optimisation System, it enables teams to optimise athlete health and performance while reducing injury risk and increasing overall performance potential. 

Kitman Labs opened its first US office in Menlo Park, California, in 2014 and is building its presence with US professional and collegiate level sports teams. In less than four years, it is now working with more than 40 teams across 15 leagues in four continents.  Kitman Labs partners with elite and professional sports organisations around the world to enable teams to prevent the risk of injury and increase player availability.

## The System
Their unique Athlete Optimization System was developed by their rich team of sports and data scientists and practitioners. Athlete OSTM 
is a cloud-based software system that works on any device connected to the Internet. It is used to help teams reduce the risk of injury 
while optimizing their data to make informed decisions. The Athlete OSTM system comprises of three parts
* Workload assessment
* Motion capture
* The Profiler system. 

## Workload Assessment
Elite athletes spend their days training, practicing or competing. Each of these activities is intense and puts a great deal of stress on 
the body, which the athlete needs time to recover from. If there's too much work and/or not enough recovery, the athlete will break down 
and get hurt. The Kitman Labs system tracks activity based on coach input or third-party data sources to fully understand how much each 
athlete is working. It identifies peaks in training workload, tracks fatigue and allows coaches and trainers to adjust so their athletes 
don't do too much. The system also factors in how athletes are feeling and  what they do outside the training/playing environment. 
Athletes answer questionnaires on their smartphones covering their sleep, mood, stress and soreness. Based on this comprehensive 
assessment, coaches can pay particular attention to athletes whom the system identifies as at risk of injury.

## Motion Capture
Kitman Labs has a patent-pending motion capture technology that enables fast and accurate biomechanical screenings, allowing coaches to 
assess their athletes in minutes rather than hours. The data from the tests performed by this technology is impressive. The system 
produces an extremely detailed wireframe model of a person, indicating each and every joint. One of the most impressive aspects of this 
technology is when an athlete jumps, the system can determine if the athlete produces slightly less force with one leg rather than the 
other. This would indicate a slight imbalance, which, if left unaddressed, could result in an injury—extremely powerful data for a coach. 
Also, since athletes can move through the tests quickly, they can go through a pre-workout screen that identifies any potential issues 
that could cause a problem that specific day.

## Profiler System
The Profiler System compiles the data from the workload assessment and motion capture. If the algorithms identify an athlete at risk, the 
system alerts the coach so he or she knows the athlete needs special attention. If an athlete is at extreme risk, the coach is notified 
to get ahead of a potential injury. The key here is proactive. Elite and professional sports organisations are very good at reacting to 
injuries. If an athlete tears an ACL, doctors and physical therapists can get that athlete back on the field in less than a year. But 
what if they could prevent that injury from happening in the first place? The information generated by the Kitman Labs system allows 
coaches and medical staffs to get in front of many injuries. So far, the results have been promising.

## Clients
Initial customers are comprised of professional level rugby teams, such as the four Irish provinces, Grenoble, Bath and Sale, and Premier 
League soccer teams, such as Everton and Norwich City. Kitman Labs have also added NFL team Miami Dolphins and NBA team Detroit Pistons 
to their ever expanding client list. Kitman Labs report that they have reduced their clients injury profiles by 30-32 percent. For NFL, 
NBA and other professional sports teams that use the system, more players were available to play, improving their seasons and each team's
odds of winning. It is estimated that it costs US sports teams $500 million in salaries for players who are forced to miss games through 
injury. To reduce their clients injury profiles by 30-32 percent, represents a massive saving to Kitman Labs clients.

## Quantifying Injury Risk 
Stephen Smith discusses the importance of Kitman Labs' role in identifying and quantifying injury risks.
  https://www.youtube.com/watch?v=AO1Q9_SX_Us


## Future Goals
The challenge for Kitman Labs? Growing beyond professional sports. They state that they see a system like theirs as a benefit to all 
athletes. Believing that if there's an opportunity to reduce injuries, it needs to be explored. But while currently lower-level coaches 
and athletes may not have the resources to acquire and use such a comprehensive system, founder Stephen Smith believes that a time will 
come when they will and that the future for Kitman Labs is that they'll be the gold standard platform across all sports.

<p align="center">
  <img width="200" height="160" src="https://raw.githubusercontent.com/DragonflyStats/MA4128Assessment/master/images/Rlogo.jpg">
</p>



## R Code

```r
library(FactoMineR)
data(decathlon)
res <- PCA(decathlon,quanti.sup=11:12,quali.sup=13)

plot(res,invisible="quali")
plot(res,choix="var",invisible="quanti.sup")
plot(res,habillage=13)

aa=cbind.data.frame(decathlon[,13],res$ind$coord)
bb=coord.ellipse(aa,bary=TRUE)
plot.PCA(res,habillage=13,ellipse=bb)

res$eig
x11()
barplot(res$eig[,1],main="Eigenvalues",names.arg=1:nrow(res$eig))
res$ind$coord
res$ind$cos2
res$ind$contrib

dimdesc(res)
```
