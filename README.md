# Devigger Help Guide

## Quick Tips
- A comma separates legs
- A "/" symbol separates sides of a market
- The first number in a leg is the side of the market you are wagering on.
- If a leg has multiple sides in its market (ie: superbowl winner), then separate all sides by a "/" symbol like this: +500/+250/+2000

## Video Tutorials

@TheeDegenBoosts on [Twitter](https://twitter.com/TheeDegenBoosts) and [YouTube](https://www.youtube.com/@TheeDegenBoosts) is making video tutorials for the devigger.
As well as, [@EVBetsMA](https://twitter.com/EVBetsMA) on Twitter who made a tutorial for the Combo Breaker.

Check them out here:

1) Devigger Tutorial Part 1 - Intro

    - Covers the basics like normal 2-way devigs, boosts, devig methods, free bet EV conversions, parlays and multi-way pre-made markets
    - [Twitter Link](https://twitter.com/TheeDegenBoosts/status/1660185736660893696) - [Youtube Link](https://www.youtube.com/watch?v=a1WH28Lz3aM)

2) Devigger Tutorial Part 2 - Correlation

    - Covers correlation and SGPs
    - [Twitter Link](https://twitter.com/TheeDegenBoosts/status/1660927966858080262) - [Youtube Link](https://www.youtube.com/watch?v=VjxE9fWW_4o)

3) Devigger Tutorial Part 3 - Functions: AVG, MAX, MIN, HIT

    - Covers how to use those functions
    - [Twitter Link](https://twitter.com/TheeDegenBoosts/status/1668859043287293952) - [Youtube Link](https://www.youtube.com/watch?v=uYLBJKzBHcg)

4) Devigger Tutorial Part 4 - Comments, Sharing Devigs, Implied EV%, Juice Estimation, INT Function

    - Covers how to use those functions
    - [Twitter Link](https://twitter.com/TheeDegenBoosts/status/1669409061731745801) - [Youtube Link](https://www.youtube.com/watch?v=buPjiu0VOAM)

5) Devigger Tutorial Part 5 - OR operators

    - Covers how to use the different OR operators for mutually exclusive and independent events
    - [Twitter Link](https://twitter.com/TheeDegenBoosts/status/1670300344365076480) - [Youtube Link](https://www.youtube.com/watch?v=YetLM9NMaJ0)

6) Combo Breaker Tutorial Part 1 - Basic

    - Covers the basics of how to use the [Combo Breaker](http://crazyninjamike.com/public/sportsbooks/sportsbook_combo_breaker.aspx)
    - [Twitter Link](https://x.com/EVBetsMA/status/1728871227987742816?s=20)

## SGP Correlation Tips

If you have a SGP that is for DeRozan to score 30+ points and DeRozan's team, the Bulls, to cover -9.5 spread, there is a positive correlation and SGP odds reflect that. You can use the devigger to place all combinations of a SGP to estimate fair odds with correlation like:

    1. DeRozan 30+ and Bulls -9.5 = +180
    2. DeRozan 30+ and Heat +9.5 = +250
    3. DeRozan <30 and Bulls -9.5 = +390
    4. DeRozan <30 and Heat +9.5 = +260

Plug that into the leg odds box like so: 180/250/390/260

It will output the fair odds of DeRozan 30+ points and Bulls to cover -9.5 spread, taking into account the positive correlation between the 2 legs.

## Juice Tips:

- If you only have one side of a market, you can specify the juice amount and the app will calculate fair odds based on the juice you specify.
To Specify juice, simply format like so: +285/15%

- If you have a similar market from that sportsbook that you'd like to derive the juice from and use that market's juice,
To Derive juice from another market, simply format like so: +285/[-116/-106]

- If a sportsbook has both a 2-way and a 1-way alt-line for a betpoint (ie. Over/Under 34.5 and 35+), you can then derive the juice% being applied to the other alt-lines.
To Derive juice from the alt-line market, simply format like so: -270/[-135=-110/-110]

Where:

    - 110/-110 is 2-way line for Over/Under 34.5
    - 135 is the same book's juiced alt-line for 35+
    - 270 is the line you want to devig and is the juiced alt-line for 30+

-  If you'd like to simply let the devigger estimate the juice% of a 2-way market, simply do: +600/juice%. It will estimate the juice% based on historical odds for moderately juiced 2-way markets (like player props)

## Mutually Exclusive Events (XOR) All-Way:

- If you have a bet on a single event, like a Nascar race, and the bet is for either Player X OR Player Y OR Player Z to win, you can format like so:
+500^+800^+1000/1200/1600/2000

In this example, there are 6 total race car drivers and you need X, Y, or Z to win. Notice that the "^" symbol combines those sides of the market so that only one needs to win. Other sides of the market should be separted by a "/" as normal. 

Note, this is mutually exclusive because there can be only one winner, not two.

## Mutually Exclusive Events (XOR) 2-Way:

- If you have 2 separate markets for the Nascar race winner instead of an outright market, you can do this:

        - +500/-700 = 2-way market for "Player X"
        - +800/-1300 = 2-way market for "Player Y"
        - +1000/-1800 = 2-way market for "Player Z"
        - +500/-700^^+800/-1300^^+1000/-1800

But note that when doing this method (^^), I recommend you use additive/shin instead of multiplicative or power methods.

This is because if you were to devig for ANY driver to win to win the race like this:
+500/-700^^+800/-1300^^+1000/-1800...etc for all drivers in the race

Then, when you summed up all of the fair value percentages, multiplicative would be over 100% (for any driver to win the race), power method would be below 100% and additive/shin would be around 100%. For this reason, additive/shin should be more accurate when devigging mutually exclusive events when using the "^^" symbols on 2-way markets

Note, this is mutually exclusive because there can be only one winner, not two.

## Independent Events (OR):

- If you have a bet on multiple events and you only need one of them to hit, such as either Player X to get 25+ points OR Player Y to get 10+ rebounds, you can format like so:

115/-110||-185/+140

Notice that instead of a ",", we used a "||" to establish that either of these 2 events can hit in order to win our bet. You can, of course, add other legs that are also "||" and you can also add other legs that are "," to specify that they must hit, such as Player X to score 25+ points OR Player Y to get 10+ rebounds, AND their team to win the game.

Events separated by a "||" are independent events and both could win, both could lose, or either could win/lose. As long as one of them wins, then the combined legs will count as a win.

## Mutually Exclusive (XOR) VS Independent Events (OR) Tips:

A quick summary of when to use the different operators:

^ = Replaces a '/' symbol

^^ = Replaces a ',' symbol. Only one of the 2 should be able to hit (like a Nascar Race)

|| = Replaces a ',' symbol. Both of the 2 should be able to hit (like either player to get 10+ points)

## Fair value:

- If you already have the fair value odds for something, for example you know something is fair value of +200, you can simply put +200 without any "/" symbol(s). It will assume the other side of the market is -200.

# Correlation Textbox Warning:

Be aware that using the method below to derive correlation from a SGP is not exact because of SGP's extra juice.
The correlation textbox assumes there is no extra juice added to a SGP (on top of the normal lines' juice). So, one thing to keep in mind with the correlation textbox, is that if a book adds extra juice to their SGP, then the correlation textbox will see that as positive correlation (when in reality, it is just extra juice).

For example, if you have -110,-110 in a SGP. Without correlation, the SGP would be:
+264. +264=-110,-110 //This would return r=0

With positive correlation of r=0.04 it might be +250:
+250=-110,-110 //This would return r=0.04

But also, if a book decides to add some extra juice to the SGP, on top of the normal lines' juice, then it could also have odds of +250, even though there should have been no positive correlation. Because of this, the normal 4/6/8 way SGP devig method is still the preferred way to devig a SGP. But it is, of course, not practical (or even possible) for a 5+ leg SGPs, or for SGPs without an under.

## Correlation Textbox:

Please read the above warning before or after reading the below guide on the correlation textbox.

- If you can't do every combination of a SGP to derive correlated fair odds, you can use the correlation textbox.
- If you already know the correlation coefficient that you like'd to apply to your parlay, simply type it in like, "0.2"
a value of 1 would be 100% positive correlation (if one hits, the other will hit). A value of -1 would be 100% negative correlation (if one hits, the other can't hit).
- If you don't already know the correlation coeficient, you can derive it by supply the SGP odds and that sportsbook's one-sided odds for each leg.
For example, let's say we are doing a SGP for Chiefs to win and Travis Kelce to score a touchdown.
FanDuel has only one side for Travis to score a touchdown and we don't have 2 sides to the market.
We know that Chiefs are a -210 on FD and Travis Kelce is a -135 to score a touchdown.
Their SGP together is +134
We can provide the correlation box with:
+134=-210,-135
It will then derive the correlation coefficient from the sportsbook and apply it to the devig's fair odds.

If you were to bet 2 uncorrelated odds that were -210 and -135, the parlay would be +157.
The SGP above at +134 is lower (and lower payout) because Chiefs and Travis Kelce have positive correlation.
Since they are positively correlated, it is more likely to hit and thus the odds/payout is lower.

You can use FD or DK's SGP to derive correlation and then use a sharp book like Pinny in the Leg Odds box as the actual odds to devig.

If you have 2 legs that are correlated, but a 3rd leg that isn't correlated, you can simply write it out as above and the  devigger will figure it out. Such as:
Leg Odds Textbox: +125/-130,+150/-180,-200/170
Correlation Textbox: +300=+125,+150
The devigger will see that the correlation textbox only has 2 legs and connect those to the first 2 legs in the Leg Odds textbox.
You must keep them in the same order in both textboxes for the legs you want to be correlated.

You can have multiple correlations by separating them by a ";" symbol. Such as:
Leg Odds Textbox: +125/-130,+150/-180,-200/+170,-165/+140
Correlation Textbox: +300=+125,+150;+120=-200,-165
The devigger will see the order in both textboxes and match them based on the order.

You can also specify correlation manually for a certain number of legs. Such as:
Leg Odds Textbox: +125/-130,+150/-180,-200/+170
Correlation Textbox: 2=0.13
This tells the devigger to correlate the first 2 legs in the LegOdds textbox with an r  of 0.13

You can also specify multiple correlations manually for a certain number of legs. Such as:
Leg Odds Textbox: +125/-130,+150/-180,-200/+170,-165/+140
Correlation Textbox: 2=0.13;2=0.41
This tells the devigger to correlate the first 2 legs in the LegOdds textbox with an r  of 0.13, and the next 2 legs with an r of 0.41

You can mix and match the above correlation options by simply separating them by a ";". Such as:
Leg Odds Textbox: +125/-130,+150/-180,-200/+170,-165/+140
Correlation Textbox: +300=+125,+150;2=0.41
This tells the devigger to derive the correlation for the first 2 legs in the LegOdds textbox, and then set the next 2 legs to be correlated with an r of 0.41

## Boosts:

If you have a profit boost on a site and you are trying to find the best bet to use it on.
Your Final Odds can be your unboosted odds and you can simply use the "Boost" checkbox to apply your boost percentage.
If it is a profit boost, choose "Profit Boost". If it is boosting the entire wager (such as BetMGM sometimes does), then choose "All".
This saves you time from having to continue to adjust the Final Odds textbox and adjusting it to be the boosted odds.

You can also perform basic math in the Boost textbox. So, MGM boosts the entire bet but the boosted winnings is returned as a free bet. If you have a 100% MGM boost and can convert at 70% free bet conversion, you'd check the "All" boost option, and then in the boost textbox, type: "100%*70%".

## Market Average Function:

If you have multiple lines that you'd like to use, you can average them to get a market average. For example, let's say that:
FanDuel has Bengals at -150 and Saints at +135.
DraftKings has Bengals at -145 and Saints at +125
You can use them as you normally would by simply including each side in an average. See below:

AVG(-150,-145)/AVG(+135,+125)

Optionally, you can label each side to keep things more organized.
AVG(Bengals:-150,-145)/AVG(Saints:+135,+125)
Notice that the ":" symbol ends the name and begins the odds.

You can use AVG anywhere you normally would have provided a single number. Such as for a 3 way moneyline in which you need a team to win or draw:

DraftKings has Arsenal -185, Draw +350, Leeds +500
FanDuel has Arsenal -180, Draw +343, Leeds +536
AVG(Arsenal:-185, -180)^AVG(Draw:+350,+343)/AVG(Leeds:+500,+536)
Notice that the XOR "^" symbol above works as normal.

You can also use it to market average one side and estimate juice on the other side(s):
AVG(-500,-450,-550)/10%

You can also do it for ATTD if you have one over/under and a lot of one way markets:

Leonard Fournette ATTD
DraftKings -125
FanDuel -110
SuperBook -136/+102
AVG(Fournette ATTD:-125,-110,-136)/+102
OR Doing the same but instead of using the +102, simply using the 2 way market's juice% to estimate the Under 0.5 TD:

AVG(Fournette ATTD:-125,-110,-136)/[-136/+102]

## Market Median Function:

The Median Function is the same as the Average Function above, except that it takes the median of a set of odds.
When supplied an odd set of numbers, it will choose the middle value.
When supplied an even set of numbers, it will average the middle 2  values.

The advantage of the Median Function over the Average Function is that it factors out outliers and mistake lines.
This makes it useful in automation to not allow a mistake line from making both sides of a bet look +EV.
For manual devigging, however, AVG() is still likely better, as it includes more data points. And mistake lines are easy to spot when manually devigging.

## MIN/MAX Functions:

Similar to the AVG function above, you can also use the MAX and MIN functions in the same format.
Such as:

MAX(-500,-450,-550)
would return  the maximum/longest odds, being -450

And:
MIN(-500,-450,-550)
would return  the minimum/shortest odds, being -550

## HIT Function:

You can supply a hit% and have it converted  to American Odds for you.

Simply:

HIT(50%)
returns +100

You can use it anywhere you'd use American Odds (in the Leg Odds textbox).

You can also perform some basic math in the Hit() function. So, if something has historically occurred 18/61 times this season, you could simply type HIT(18/61) and it will be the same as HIT(29.5%), which is the same as +239 fair value.

## Linear Interpolation Function:

If you need for a player to have over/under 299.5 passing yards, and you only have 294.5 and 319.5, you can simply use the INT() function to linearly interpolate what 299.5 odds would be.

#### Example #1:

    Over 294.5 = -220
    Over 319.5 = -130
    Desired is  Over 299.5
    INT(299.5;294.5=-220,319.5=-130)

This would return  -197 odds. This is between -220 and -130, being closer to -220 since it is 299.5 is closer to the 294.5

You can also do this for anywhere you would normally put odds in the Leg Odds textbox.

#### Example #2:

    Over 294.5 = -220
    Over 319.5 = -130
    Under 294.5 = 180
    Under 319.5 = 105
    Desired is  Over/Under 299.5
    INT(299.5;294.5=-220,319.5=-130)/INT(299.5;294.5=180,319.5=105)

This would return -197/+161
You can do the above and then also use the correlation checkbox to apply correlation to these legs.

You can also do it for something like a 4-way SGP devig:

#### 
Example #3:
Pretend we have a boost that is "Patrick Mahomes to Pass for 300+ Yards and Chiefs to Win vs Raiders"

    Chiefs win and Over 294.5 = -120
    Chiefs win and Over 319.5 = +120
    Chiefs win and Under 294.5 = +230
    Chiefs win and Under 319.5 = +150
    Raiders win and Over 294.5 = +475
    Raiders win and Over 319.5 = +575
    Raiders win and Under 294.5 = +950
    Raiders win and Under 319.5 = +700

INT(299.5;294.5=-120,319.5=+120)/INT(299.5;294.5=+230,319.5=+150)/INT(299.5;294.5=+475,319.5=+575)/INT(299.5;294.5=+950,319.5=+700)
This would return -112/+210/+493/+888

You can also use this function in the correlation textbox

#### Example #4:

    Chiefs win and Over 294.5 = -120
    Chiefs win and Over 319.5 = +120
    Chiefs win leg = -425
    Over 294.5 leg = -220
    Over 319.5 leg = -130
    INT(299.5;294.5=-120,319.5=120)=-425,INT(299.5;294.5=-220,319.5=-130)

This would return -112=-425,-197 for the correlation textbox

You an also use the AVG() function with the INT() function like so:

#### Example #5:

You want to average the Over 300+ line from DK and FD.  FD has the exact 300+ line. But DK only has the 294.5 and 319.5.
We can interpolate the DK lines and then average that in with the FD line.

    FD Over 299.5 = -210
    DK Over 294.5 = -220
    DK Over 319.5 = -130
    AVG(-210, INT(299.5;294.5=-220,319.5=-130))

returns AVG(-210, -197)
returns -203

## Multi-line Textbox and Comments:

If you would like to write notes about a devig, you can do so in the LegOdds textbox.
Simply write "//" and anything followed by "//" on a line will be ignored by the devigger.
For example:

    -110/-110//Devigged vs Pinny

You can enable the multi-line textbox for LegOdds textbox at the bottom of the devigger page, as a setting.
You can change the width/height of the multi-line textbox by dragging the bottom right corner of it.

After doing this you can organize your devig with new lines and comments.
For example:

    //Lakers and Celtics to both win, FD boost
    -300/200,//Lakers ML (Pinny)
    -500/390//Celtics ML (Pinny)

On the above multi-line LegOdds textbox, notice that we still must provide the "," on the 2nd line to tell the devigger it is a parlay. The devigger will simply ignore comments and combine the multi-lines into a singleline.

You can also do multi-line  comments by starting with "/*" and ending the multi-line comment with "*/".
For example:

    //Lakers and Celtics to both win, FD boost
    -300/200,//Lakers ML (Pinny)
    -500/390//Celtics ML (Pinny)
    /*
    Additional details or notes on the devig
    could go here and you can do it on
    multiple lines to more freely type.
    */

You can also write comments in the FinalOdds, Correlation and Boost textboxes (but no multi-line for those boxes).

## Implied EV%:

You can supply an EV% and the devigger will derive what the fair value is and calculates your Kelly Wager.

Simply type in the leg odds textbox:

EV=5%

And in the Final Odds textbox, supply a normal American Odds (no daily fantasy syntax/format)

This is useful if you see a play that someone shared and  they mention the EV% but not the fair odds.
Now you can use the EV% they supply in order to calculate it and figure out what Kelly Wager is recommended.

## Final Odds Format:

The normal Final Odds format is to simply supply American Odds (like +300).
But there is a much more robust format that can be utilized for devigging everything from promos to daily fantasy. The new format allows you to do all of the following:

1. Risk-Free Bet - Lose bet, get free bet back
2. One leg insurance SGP Risk-Free Bet - Miss one leg, get free bet
3. Lose all legs Risk-Free Bet - Lose exactly all legs, get a free bet
4. Win & Get Promo
5. Bet & Get Promo
6. Daily Fantasy Flex Payouts - Different payouts based on how many legs hit
7. Ability to perform math to calculate a reward's value or specify the free bet's conversion%

And much more! The format is so versatile that it can likely handle many new promos that come out.
To learn more about this new format, see the below section, "Daily Fantasy". It will explain everything about the format, including tricks and shortcuts!

## Daily Fantasy:

PrizePicks and Underdog Fantasy are examples of Daily Fantasy sites. They are not sportsbooks.
They only offer parlays and mostly player props. There are a lot of promos that they do that are +EV.

PrizePicks calls its normal parlay's "Power Plays" and Underdog Fantasy only offers normal parlays.

PrizePicks has an interesting parlay type called "Flex Plays". Their 5-pick flex play will pay out:

    10x if all 5 picks win
    2x if any 4 picks win
    0.4x if any 3 picks win

Because of this, flex pay essentially has a dynamic "Final Odds" based on the fair chance of your legs to hit.

For all of the Daily Fantasy parlay types, you can choose it from the Daily Fantasy DropDown list.

After  choosing a parlay type, it will populate the Final Odds Textbox with the required payout pattern for that parlay.

If for some reason there is a boost or you need to change the Flex's payout pattern, the format is:

NumberOfLegsRequiredToHit=PayoutX

And additional payout options can be separated by semi-colons.
For example, this is the PrizePicks Flex payout for a normal 5-pick Flex:

5=10x;4=2x;3=0.4x

This translates to:

    if 5 picks win, you get 10x payout
    if 4 picks win, you get 2x payout
    if 3 picks win, you get 0.4x payout

You can also do a normal parlay that is 5 legs (like Underdog Fantasy) with a 20x payout like:
5=20x

Also, if you want it to work for any number of legs that you have and it is a normal parlay, you can simply type:
20x

Daily Fantasy can be a little confusing when getting started. If you need more help, feel free to ask for help in my CNM discord.

You can also specify American Odds in place of decimal odds. Simply write it as:

    Decimal Odds: 4=5x;3=1.5x
    American Odds: 4=+400;3=-200

You can also specify invidual leg odds  if you have a parlay insurance.

American Odds: 3=-500,-450,-325;2=0.7x

In the above example, you win your normal 3-way parlay if you hit all 3. You get 0.7x (70%) of your stake back if you miss just one.

This 70% represents a 70% free bet conversion.

You can also use this FinalOdds format for Win&Get and Bet&Get promos.

Example:

Bet on the Ravens vs Bengals moneyline and receive 100% of your stake as a free bet, up to $25, if you win.
Assuming the free bet value is 70% and we decide to bet on the Bengals at a -260.
We can put in the FinalOdds textbox:

    1=-260;w=0.7x
    OR
    1=-260;w=100%*70%

This says, if we win the bet as normal, the final odds are -260. But we also receive a free bet (70%) if we also win.

Another way can use this FinalOdds format for Bet&Get promos.

Example:

Bet $50 on the Lakers vs Bucks game and receive $1, as a free bet, for every 3 pointer made.
You estimate, based on historical data, that there will be around 25 3 pointers.
So, you are estimating that you will receive, on average, a $25 free bet (at an estimated 70% conversion)
You decide to bet on the Bucks at -600 odds

You would use this in the Final Odds textbox:

    1=-600;n=0.35x
    OR
    1=-600;n=$25/$50*70%

This says, if we win the bet as normal, the final odds are -600. And no matter what, win or lose, we estimate to receive a $25 free bet.

To get the 0.35x, we use the formula:

$FreeBet / $PrimaryWager * 70%Conversion = 0.35x

Which means, the free bet is worth 35% of our primary wager (or 0.35x).

A shortcut when doing risk-free bet promos. Instead of doing:
4=+300;3=0.7x;2=0.7x;1=0.7x;0=0.7x
You can instead do:
4=+300;r=0.7x
"r" will cover all cases  for when your bet loses.

Another shortcut is that you can put "#" as the max number of legs you have. For example:

2=+300;r=0.7x
can be  replaced with
#=+300;r=0.7x

The devigger will know that you meant the maximum number of legs (ie. all legs must hit, or winning your bet).

Have you ever bet 2 +EV bets that are mutually exclusive?

You can estimate how much more kelly you should be putting on mutually exclusive bets, if only one can hit.
Let's say you are betting on a game's moneyline and there is no chance of a tie/draw. One must hit. They are mutually exclusive.

Let's say fair value for both is exactly +100 odds. 50% chance that TeamA wins, 50% chacne that TeamB wins.
If a book offered you +150 on TeamA, the EV% would be 25%, full kelly of 16.67u (16.67% of bankroll).
If a book offered you +150 on TeamB, it'd be the same EV% and full kelly.

If you bet them both like that, you'd only be putting up 33.34% (16.67%+16.67%) of your bankroll, even though it is 100% (50%+50%) chance to hit!

To factor this in, you can devig them using mutually exclusive operator (+100^^+100) in the Leg Odds textbox.
In the Final Odds textbox, put both outcome's betting odds (+150^^+150).

The Fair Value will output as 100% chance to hit. The full kelly suggested to wager between the 2 bets would be 100u (100% of your bankroll).

To determine how much to put on each bet, take the fair value of that side (50%), divide it by the mutually exclusive fair value (100%). So, you'd want to put

50% of the 100u on TeamA and 50% of the 100u on TeamB. That means it suggests to put 50% of your bankroll on each.
I am using full kelly as an example to make it easier to see the math.

The key takeaway from this type of bet/devig is that when you bet multiple +EV bets that are mutually exclusive, the kelly wager should theoretically increase.

You can also do the same as the above for independent events (ones which can both hit).
To do that, you'd simply put t his in the Final Odds textbox:

+150||+150

## Why does the Devigger return different Final Odds for each devig method when I use "n=" in the Final Odds textbox?

Let's look at some examples of the math and see that the devigger is handling things correctly in these cases.

Let's assume we have a 50% fair hit% and simple FinalOdds of +100
This would return:

(($100 * 2) * 50% - $100) / $100 = 0% +EV

The first part of the equation ($100 * 2) is your  payout if you win. Multiplied by the chance to win (50%). Subtracting the wager cost ($100). And dividing by your primary wager  ($100). This returns 0% +EV.

Let's look at one that is more complex.

- 1000/600 fair returns 86.4% hit% for multiplicative.

A simple FinalOdds of +100,
This would return:

(($100 * 2) * .864 - $100) / $100 = 72.8% +EV

Same formula as before. Math checks out, so far.

Factoring in a Bet&Get:

(($100 * 2) * .864 - $100 + $100) / $100 = 172.8% +EV

The devigger returns a correct 172.8% +EV

And it returns the correct EV% for each devig method.

And it has slight different Final Odds for each method.

However, if you also took those FinalOdds that get outputted for each devig method into a separate devigger, with those same Leg Odds, you'd get the exact same EV%. So, it may seem strange that the Final Odds would change for a Bet&Get promo based on the Hit% changing, but (unless I'm wrong lol) it is correct.

## Multiplicative/Normalization/Traditional Devig Method:

- This is the normal way that we devig, but it does not take into account underdog bias. This method has a +900/- 3000 outputting +968 fair odds.

## Additive Devig Method:

- This is another way to devig. It helps to take into account underdog bias. This translates to a +900/-3000 outputting +1412 fair odds.
- Note that there are rare instances where the fair value will be a negative percentage. This is normal and expected of the Additive devig method.

## Power Devig Method:

- This is another way to devig. It exponentially takes underdog bias into account. This translates to a +900/-3000 outputting +2192 fair odds.

This method heavily leans towards heavy favorites.

## Shin Devig Method:

- This is another way to devig. For Shin, 2 way markets will devig to the exact same fair odds as Additive. However, when devigging 3+ way markets, Shin will produce different fair odds than Additive.

## Worst-case Devig Method:

- This method will always use the lowest implied probability of either Multiplicative or Additive or Power or Shin (set in the settings). This way you play it safe and go off of the worst-case scenerio ev%.

## Weighted Average Devig Method:

- This method will always use weighted average of the implied probabilities of any of the 2 or 3 or 4 main devig methods (set in the settings). This way you can use a combination of percentages that is (hopefully) more accurate/optimal than a single devig method, and less conservative than the Worst-case Devig method.

## Theoretical Hedge Method:

The Theoretical Hedge Value (THV%) is similar to HV% (Used on [www.CrazyNinjaOdds.com](www.CrazyNinjaOdds.com))
The Hedge Value (or HV%) is a metric that can be directly compared to EV%.

HV% tells you the guaranteed profit (or loss) you could make if you hedged every possible combination of bets.

If a promo is for a $20 wager and the HV% is 10%, then you could hedge the promo for a guaranteed profit of $2.
If a promo is for a $20 wager and the EV% is 10%, then your expected (long-term) profit is $2.

THV% is similar to this HV% but it can sometimes differ from an HV% based on a number of factors.

If you provide multiple odds with the AVG() function, the THV% will be calculated using the best odds provided.

If the THV% is positive, you can almost guarantee there is value in your bet.
It is sort of a  "true worst-case" devig method. It was created to help be a deciding factor in questionable markets with a lot of juice.

## Why Are There Different Devig Methods and Which One is Best?:

(Note: The below is based on my understanding and under the assumption the sportsbooks would do what I would do if I were them)

- Longshot bias. In order to best explain, let us see it from the point of view of a sportsbook:

Across all devig methods, let us always assume the sportsbook runs its analysis of the game and their computer spits out the true/fair odds are for the Steelers to have a 70% chance to win. This is true/fair odds and is 70% without any juice involved.

And let us also assume, for simplicity, that the total money wagered on both teams (combined) is $100. And let's assume the sportsbook has 8.3% juice in the market.

Steelers vs Browns moneyline. The sportsbook thinks the Steelers have a 70% chance to win (browns a 30% chance). We are the sportsbook and we want to make the same amount of money, no matter which team wins. We must adjust our odds/payouts based on how much money is on the Steelers vs how much money is on the Browns.

### (Multiplicative):
In a perfect world, we would assume 70% of the money would go on the Steelers, 30% on the Browns.
This is the multiplicative method's way of thinking.

As a sportsbook, we would set the odds to:

    -314 = 1.32X payout multiplier
    +208 = 3.08X  payout multiplier
    -314/+208 = 70% fair value devig multiplicative

If we know that 70% of the money is on Steelers, 30% is on the browns, that means:

If the Steelers win, we get = ($70 + $30) - ($70) * 1.32 = $7.6

the sportsbook made $7.60 off of the game/bets. $7.6/$100 = 7.6% ROI

If the Browns win, we get = ($70 + $30) - ($30) * 3.08 = $7.6

the sportsbook made $7.60 off of the game/bets. $7.6/$100 = 7.6% ROI

(Formula = ($TotalMoneyWageredOnSteelers + $TotalMoneyWageredOnBrowns) - ($TotalMoneyWageredByWinningBettors) * (PayoutMultiplierForWinningBettors)

The sportsbook adjusted the payout/odds so that they would make the same no matter which team won. As it was a 70% chance for Steelers to win and 70% of the money was on the Steelers, the sportsbook did not need to take into account longshot bias, as there was none in this case.

What if there was longshot bias and the sportsbook used the same odds?

Let's see what would happen:

Longshot bias says that more money will be placed on heavy underdogs because it's like a lottery ticket and people love risk and a chance to win it big. Because of longshot bias, in our example below, 68.46% of the money is bet on the Steelers and 31.54% is bet on the Browns.

So, more money was bet on the longshot/Browns than in our example above.

What if we don't change the odds/payouts, even though we know that more money is on the Browns?:

If Steelers win, ($68.46 + $31.54) - ($68.46) * 1.32 = $9.63
If Browns win, ($68.46 + $31.54) - ($31.54) * 3.08 = $2.85

As a sportsbook, we want to make the same profit no matter what, and maximize our longterm profit.

So, we must adjust the odds/payouts to take into account the longshot bias (and more people betting on the underdog).

As a sportsbook, we would set the odds to:

-287 = 1.35X payout multiplier
+193 = 2.93X payout multiplier
-287/193

If we know that 68.46% of the money is on Steelers, 31.54% is on the Browns, that means:

If the Steelers win, we get = ($68.46 + $31.54) - ($68.46) * 1.35 = $7.579

If the Browns win, we  get = $68.46 + $31.54) - ($31.54) * 2.93 = $7.5878

The sportsbook made the same profit and ROI% no matter which team won.

Back to our perspective as sports bettors:

We cannot see exactly how much money is wagered on either side of a bet like the sportsbooks see.
We can estimate, however, and by using the Multiplicative devig method in our first example (when there was no longshot bias), it would return the same fair value (70%). And by using the Additive devig method in our second example (when there was longshot bias), it would also return the same fair value (70%).
The right devig method depends on how much longshot bias there is in the market.

So, when is it best to use the different devig methods? It really depends. The worst-case devig method will be the most conservative in estimating longshot bias. But ideally, if we had enough data, we could estimate the longshot bias based on a number of factors such as:

market type, sportsbook, sport, game popularity, etc.

There is essentially a range of where the fair chance could be and worst-case method will give you the lowest of the estimates.

I personally prefer the worst-case method but I hope that with my new scraping site, we will eventually have enough data to analyze and determine what the true fair chance of a bet are to hit based on the factors mentioned above.
