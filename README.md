Let's make a game!
name:Peanut Butter Cupper DEV
by:morkysherk
desc:Make some tasty peanut butter cups!<.>Created on <b>December 2nd, 2017</b><.>Last updated on <b>January 23rd, 2018</b>
forum post:16768

//hello
//link:http://orteil.dashnet.org/igm/?g=zW2QJL98

Settings
	tiling background:https://imgur.com/bIMzkmq.png
	spritesheet:numbers, 48 by 48, https://imgur.com/ybrBc03.png
	spritesheet:hat, 48 by 48, https://cdn.rawgit.com/morkysherk/8a61b7be3b0312ef38861b766d066f83/raw/3a2bb60e9fb5e34100400c86987cdc1cbe866d6b/mana%20hat2.svg
	spritesheet:cursor, 48 by 48, https://cdn.rawgit.com/morkysherk/1ccc5a7be2a39e0f69dc75cfb75a3f30/raw/53e40164a1418a8bc13e2decdfff69cbd2d039ac/cursor2.svg
	building cost refund: 1%
	stylesheet:https://pastebin.com/xu9921Ly
		//All IGM games are copyrighted to their respective owners, by the way

Buttons
	*TEMPLATE
		class:inFront
     *chocoButton
          name:Chocolate Button
          desc:Click to make more chocolate!
	 icon:https://cdn.rawgit.com/morkysherk/2ab934765c73cf597da21b771b167d6b/raw/82b448527d51539329e09a5fe4e8843c8f76121e/gistfile1.svg
		  on click:
				if (buttonAnimation=1) anim icon wobble2
				if (buttonAnimation=2) anim icon bounceOnce
				if (buttonAnimation=3) anim icon plop
				if (buttonAnimation=4) anim icon wiggling2
				if (buttonAnimation=5) anim icon wobbleSlow
		  end
		  no text
          on click:yield 100000000000000 chocolate
		  on click:if (chance(min(20,(0.3+(chanceIncreases*0.03)))%)) yield 1 goldBeanPod
		  on click:if (have combinedClicking) yield 0.5 peanutButter
		  on click:if (have peanutcupClicking) yield (1/3) peanutCups
		  on click:if (aaa<1) yield 1 aaa
		  on click:
			noClickSeconds=0
		  end
          class:bigButton redFlares
		  tag:cButton
	 *pButton
          name:Peanut Butter Button
          desc:Click to make more peanut butter!
		  on click:
				if (buttonAnimation=1) anim icon wobble2
				if (buttonAnimation=2) anim icon bounceOnce
				if (buttonAnimation=3) anim icon plop
				if (buttonAnimation=4) anim icon wiggling2
				if (buttonAnimation=5) anim icon wobbleSlow
		  end
		  no text
          on click:yield 1 peanutButter
		  on click:if (chance(max(25,(0.3+(chanceIncreases*0.03)))%)) yield 1 goldBeanPod
		  on click:if (have combinedClicking) yield 0.5 chocolate
		  on click:if (have peanutcupClicking) yield (1/3) peanutCups
		  on click:
			noClickSeconds=0
		  end
	   icon:https://cdn.rawgit.com/morkysherk/cfa7f4e5568f4a7eb352e2aaf79122b6/raw/5e1fead872c27b1455dc14fb9ea8b833c1d5e809/pbutton.svg
		  class:bigButton blueFlares
		  tag:pButton
	*TEMPLATE
		tag:debug
	*debug1
		name:+1k cups
		on click:yield 1000 peanutCups
	*debug2
		name:+1M cups
		on click:yield 1000000 peanutCups
	*debug3
		name:+1B cups
		on click:yield 1000000000 peanutCups
	*debug10
		name:+1T cups
		on click:yield 1000000000000 peanutCups
	*alottacups
		name:A lot of cups
		on click:yield 1e308 peanutCups
	*debug4
		name:+1k chocolate
		on click:yield 1000 chocolate
	*debug5
		name:+1M chocolate
		on click:yield 1000000 chocolate
	*debug6
		name:+1B chocolate
		on click:yield 1000000000 chocolate
	*debug11
		name:+1T chocolate
		on click:yield 1000000000000 chocolate
	*debug7
		name:+1k peanut butter
		on click:yield 1000 peanutButter
	*debug8
		name:+1M peanut butter
		on click:yield 1000000 peanutButter
	*debug9
		name:+1B peanut butter
		on click:yield 1000000000 peanutButter
	*debug12
		name:+1T peanut butter
		on click:yield 1000000000000 peanutButter
	*beanChanceUp
		name:Max gold bean pod chance
		on click:yield 10000000 chanceIncreases
	*loadsaBuildings
		name:Plenty of moleculizers
		on click:yield 182730871092837098127309812031213123123 subAtomics
	*loadsaAchievs
		name:Plenty of achievements
		on click:yield 923789487092853609890230029837408087034 achievPoints
	*100mana
		name:+100 mana
		on click:yield 100 mana
	*100pods
		name:+100 bean pods
		on click:yield 100 goldBeanPods
	*noDelay
		name:Reset spell delay
		on click:yield -100 delay
	*luckySpawn
		name:Spawn golden cup
		on click:spawn luckyCup
	*spawnfallingPod
		name:Spawn falling bean pod
		on click:spawn goldPod
	*60minutes
		name:+60 minutes played
		on click:yield 3600 secondsPlayed
	*3600noClickSeconds
		name:+3600 seconds of no clicking
		on click:yield 3600 noClickSeconds
	*1000lclicks
		name:+1000 lucky cup clicks
		on click:yield 1000 lclicks
	*1000cBeans
		name:+1000 crystal beans
		on click:yield 1000 crystalBeans
	*100000gBeans
		name:+100000 golden beans
		on click:yield 100000 goldBeans
	*upgrades
		name:All upgrades
		on click:multiply cost of :Upgrades by 0
		on click:yield :Upgrades
	*gibachievs
		name:All achievements
		on click:yield :Achievements
	*0upgrades
		name:0 upgrades
		on click:ownedUpgradetxt=0
	*0upgrCheck
		name:Upgrade check=0
		on click:upgrCheck=0

Resources

	//STATS

	*TEMPLATE
		tag:stat
		class:cleared noBackground

	//WARNINGS

	*cwarning
		name:You're not making enough chocolate!
		hidden when 0
		text:You're not making enough chocolate!
		class:roundBg
		tag:warning
	*pwarning
		name:You're not making enough peanut butter!
		hidden when 0
		text:You're not making enough peanut butter!
		class:roundBg
		tag:warning

	//EARNED

	*earned
		name:Peanut butter cups produced
		desc:How many peanut butter cups you've produced.
		is always:peanutCups:earned
		text:[?(this=1)|1 peanut butter cup produced|[this] peanut butter cups produced]
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*leftBehind
		name:Peanut butter cups left behind
		desc:How many peanut butter cups you've left behind.
		text:[this] peanut butter cups left behind
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		hidden when 0
	*earnedThisUniverse
		is always:(earned-leftBehind)
		name:Peanut butter cups produced in this universe
		desc:How many peanut butter cups you've produced in this universe.
		text:[?(this=1)|1 peanut butter cup produced in this universe|[this] peanut butter cups produced in this universe]
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:invisible
	*cleftBehind
		class:invisible
	*pleftBehind
		class:invisible
	*cEarnedThisUniverse
		is always:((chocolate:earned)-cleftBehind)
		class:invisible
	*pEarnedThisUniverse
		is always:((peanutButter:earned)-pleftBehind)
		class:invisible

	//CHOCOLATE PRODUCTION RATES

	*chocoworkerp
		name:Chocolate Worker Yield
		desc:How much chocolate your workers make every second.
		text:[chocoworkerp:ps] chocolate/s from workers
		icon:https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*chocofarmp
		name:Chocolate Farm Yield
		desc:How much chocolate your farms make every second.
		text:[chocofarmp:ps] chocolate/s from farms
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*refineryp
		name:Refinery Yield
		desc:How much chocolate your refineries make every second.
		text:[refineryp:ps] chocolate/s from refineries
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg

	//PB PRODUCTION RATES

	*buttererp
		name:Peanut Butterer Yield
		desc:How much peanut butter your butterers make every second.
		text:[buttererp:ps] peanut butter/s from peanut butterers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*converterp
		name:Converter Yield
		desc:How much peanut butter your peas and nuts converters make every second.
		text:[converterp:ps] peanut butter/s from peas and nuts converters
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*factoryp
		name:Factory Yield
		desc:How much peanut butter your factories make every second.
		text:[factoryp:ps] peanut butter/s from peanut butter factories
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg

	//MIXED PRODUCTION RATES

	*clickerp
		icon:https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		name:Autoclicker Yield
		desc:How much peanut butter and chocolate your autoclickers make every second.	
		text:[clickerp:ps] peanut butter and chocolate/s from autoclickers
		hidden when 0
	*replicatorp
		name:Replicator Yield
		desc:How much peanut butter and chocolate your replicators make every second.	
		text:[replicatorp:ps] peanut butter and chocolate/s from replicators
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/52ab77aa07ae52a02994ad81c32e93f3/raw/3f64bc9762ac1154994d513193bf03f68aa41ba6/replicator.svg
	*coreExtractorp
		name:Core Extractor Yield
		desc:How much peanut butter and chocolate your core extractors make every second.	
		text:[coreExtractorp:ps] peanut butter and chocolate/s from core extractors
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
	*qDownloaderp
		name:Quantum Downloader Yield
		desc:How much peanut butter and chocolate your quantum downloaders make every second.	
		text:[qDownloaderp:ps] peanut butter and chocolate/s from quantum downloaders
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*mindReaderp
		name:Mind Reader Yield
		desc:How much peanut butter and chocolate your mind readers make every second.	
		text:[mindReaderp:ps] peanut butter and chocolate/s from mind readers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg

	//CUP PRODUCTION RATES

	*cupperuse
		always hidden
	*cupperp
		name:Cupper yield
		desc:How many peanut butter cups your peanut butter cuppers make every second.
		text:[cupperp:ps] peanut butter cups/s from cuppers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*machineuse
		always hidden
	*machinep
		name:Machine yield
		desc:How many peanut butter cups your machines make every second.
		text:[machinep:ps] peanut butter cups/s from machines
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*printeruse
		always hidden
	*printerp
		name:3D printer yield
		desc:How many peanut butter cups your 3D printers make every second.
		text:[printerp:ps] peanut butter cups/s from 3D printers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
	*pukeruse
		always hidden
	*pukerp
		name:Puker yield
		desc:How many peanut butter cups your pukers make every second.
		text:[pukerp:ps] peanut butter cups/s from pukers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
	*rearrangeruse
		always hidden
	*rearrangerp
		name:Rearranger yield
		desc:How many peanut butter cups your rearrangers make every second.
		text:[rearrangerp:ps] peanut butter cups/s from rearrangers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*rocketuse
		always hidden
	*rocketp
		name:Trade spaceship yield
		desc:How many peanut butter cups your trade rockets make every second.
		text:[rocketp:ps] peanut butter cups/s from trade spaceships
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*portaluse
		always hidden
	*portalp
		name:Portal yield
		desc:How many peanut butter cups your portals make every second.
		text:[portalp:ps] peanut butter cups/s from portals
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*mysteryuse
		always hidden
	*mysteryp
		name:Mystery box yield
		desc:How many peanut butter cups your mystery boxes make every second.
		text:[mysteryp:ps] peanut butter cups/s from mystery boxes
		hidden when 0
	   icon:https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*subatomicp
		name:Subatomic moleculizer yield
		desc:How many peanut butter cups your subatomic moleculizers of the Greek bose-stein convapitators make every second.
		text:[subatomicp:ps] peanut butter cups/s from subatomic moleculizers
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*bhExtractoruse
		always hidden
	*bhExtractorp
		name:Black hole extractor yield
		desc:How many peanut butter cups your black hole extractors make every second.
		text:[bhExtractorp:ps] peanut butter cups/s from black hole extractors
		hidden when 0
		icon:https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*anomalyuse
		always hidden
	*anomalyp
		name:Space-time anomaly yield
		desc:How many peanut butter cups your space-time anomalies make every second.
		text:[anomalyp:ps] peanut butter cups/s from space-time anomalies
		hidden when 0
	   icon:https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg

	//TIME STATS

	*secondPlayed|secondsPlayed
		name:Seconds played|Seconds played
		desc:How long you've been playing.
		text:[?(this=1)|1 second played|[this] seconds played]
		icon:https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*minutePlayed|minutesPlayed
		name:Minutes played|Minutes played
		desc:How long you've been playing.
		text:[?(this=1)|1 minute played|[this] minutes played]
		icon:https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
		is always:floor(secondsPlayed/60)

	//CLICKS STATS

	*cclick|cclicks
		name:Chocolate Clicks|Chocolate Clicks
		desc:How many times you've clicked the chocolate.
		is always:chocoButton:clicks
		text:[?(this=1)|1 chocolate button click|[this] chocolate button clicks]
		icon:https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*pclick|pclicks
		name:Peanut Butter Clicks|Peanut Butter Clicks
		desc:How many times you've clicked the peanut butter.
		is always:pButton:clicks
		text:[?(this=1)|1 peanut butter button click|[this] peanut butter button clicks]
		icon:https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*lclicks|lclicks
		name:Golden cup clicks|Golden cup clicks
		desc:How many golden peanut butter cups you've clicked.
		text:[?(this=1)|1 golden peanut butter cup collected|[this] golden peanut butter cups collected]
		icon:https://imgur.com/ArCt4ka.png

	//OTHER STATS

	*multiplier
		class:invisible
	*multiplier2
		is always:multiplier*(max(1,(1+(divineCups/500)*(pow(1.02,angelicCuppers)))))
		name:Multiplier
		desc:Your production multiplier, in percent.
		start with:100
		text:[this]% multiplier
		icon:https://imgur.com/wc4CzdV.png
		class:invisible
	*cIncrease|cIncreases
		name:Golden bean pod chance upgrade|Golden bean pod chance upgrades
		desc:How many times you've increased your golden bean pod chance. Found by clicking golden peanut butter cups.
		hidden when 0
		is always:chanceIncreases
		text:[?(this=1)|1 golden bean pod chance increase|[this] golden bean pod chance increases]
	  icon:https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
	*goldPodSummoned|goldPodsSummoned
		name:Golden bean pod summoned|Golden bean pods summoned
		desc:How many golden bean pods you've summoned.
		text:[?(this=1)|1 golden bean pod summoned|[this] golden bean pods summoned]
	  icon:https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
	*thisstatClick|thisstatClicks
		name:Times you've clicked this stat
		desc:How many times you've clicked this stat.
		on click:yield 1 thisstatClick
		text:[?(this=1)|You've clicked this stat 1 time|You've clicked this stat [this] times]
		icon:https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*noClickSecond|noClickSeconds
		name:no click seconds
		class:invisible

	//RESOURCES

	*TEMPLATE
		tag:resource

     *peanutCup|peanutCups
          name:Peanut Butter Cup|Peanut Butter Cups
          desc:A delicious mixture of peanut butter and chocolate!
		  icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
          show earned
		  class:noBackground
		  on click:yield 1 coolResource
     *chocolate|chocolates
          name:Chocolate Bar|Chocolate Bars
          desc:A tasty snack used as the outer shell of a Reese's cup.
          hidden when 0
          show earned
		 icon:https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
		  class:noBackground
	*peanutButter|peanutButters
          name:Jar of Peanut Butter|Jars of Peanut Butter
          desc:Often used on bread, this topping also goes well with chocolate.
          hidden when 0
          show earned
	   icon:https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
		  class:noBackground
	*fireCup|fireCups
		name:Flaming Cup|Flaming Cups
		desc:woah duuude
	  icon:https://cdn.rawgit.com/morkysherk/c0eb723a7bac1dc5d514c5fcbef23b5b/raw/1da1fd6ded387a188c809c958e8f1f9f0f76b49f/fireCup.svg
		class:blurred noBackground
		class:invisible

	//SPECIAL RESOURCES

	*TEMPLATE
		tag:special
	*goldBeanPod|goldBeanPods
		name:Golden Bean Pod|Golden Bean Pods
		desc:A pod containing golden cocoa beans.
		on lose:if (chance(1%)) yield 1 crystalBean
		show earned
		class:noBackground
	  icon:https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
	*goldBean|goldBeans
		name:Golden Cocoa Bean|Golden Cocoa Beans
		desc:Rare, exquisitely flavored cocoa beans used to buy special powerful upgrades.
		show earned
		hidden when 0
		class:noBackground
	  icon:https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
	*crystalBean|crystalBeans
		name:Crystal Bean|Crystal Beans
		desc:An incredibly valuable cocoa bean with an unimaginably delicious flavor. Possessed only by successful chocolatiers, and used to purchase powerful boosts.
	icon:https://cdn.rawgit.com/morkysherk/490a801fbeba9232c76ec1f9b0a56054/raw/57ed03041c77ac8d1a7377a7221e6f8f5659a07f/crystalBean.svg
		class:noBackground
		hidden when 0
	*mana|manas
		name:Mana|Mana
		desc:Magic power used to cast spells.
	icon:https://cdn.rawgit.com/morkysherk/17878b0e6065cc04058debceaf423fb1/raw/183cf6fec09208f552ff4b4ed2dd3f58d00d4468/mana%20hat.svg
		class:noBackground
		tag:spelltxt
		text:Spells - [this] mana, [?(delay=0)|no delay|[delay] second delay]
		on earn:if (mana>=(500*pow(1.01,tallerHats)) and mana<((500*pow(1.01,tallerHats))+10)) log(maxMana) Maximum mana reached!
	*chanceIncrease|chanceIncreases
		name:Golden Bean Pod Chance Increase
		class:invisible

	*TEMPLATE

	*divineCups
		name:Divine Cups
		desc:Gifts from the peanut butter cup gods for successfully filling a universe. Can be used to purchase powerful upgrades.
		class:noBackground
	 icon:https://cdn.rawgit.com/morkysherk/b914a55433f5e3af3bab7b6d6641b29a/raw/15883d5279e720636ae9e91e83fdf33cd710055d/divinecup.svg
		show earned
		class:invisible
		tag:divine
	*frenzy|frenzy
		name:10x Multiplier Timer
		text:10x multiplier - [this] seconds remaining
		tag:timer
		hidden when 0
		class:noBackground
	*frenzy2
		name:25x Multiplier Timer
		text:25x multiplier - [this] seconds remaining
		tag:timer
		hidden when 0
		class:noBackground
	*delay
		name:Spell Delay
		desc:How much longer you must wait to cast your next spell.
		tag:eeee
	*coolResource
		name:ayyy
		desc:kajwhd
		hidden
	*effectDeterminer|effectDeterminers

	*achievPoint|achievPoints
		name:Achievements
		tag:achievPoints
		text:Achievements - <b>[this]/90 (~[((achievPoints/90)*100)]%) earned</b>
		desc:Things awarded for reaching certain milestones in the game. These will probably give you bonuses at some point in the future.
		class:noBackground
	*secretPoint|secretPoints
		name:Secrets
		tag:secretPoints
		text:Secrets - <b>[this]/6 (~[((secretPoints/6)*100)]%) discovered</b>
		desc:Things hidden throughout the game that aren't necessarily achievements. These may unlock special bonuses at some point.
		class:noBackground
	*upgradetxt
		name:Available upgrades
		tag:upgradetxt
		text:Available upgrades
		desc:Upgrades to give you boosts.
		class:noBackground
	*ownedUpgradetxt
		name:Owned upgrades
		tag:ownedUpgradetxt
		text:Owned upgrades - [this]
		desc:Upgrades giving you boosts.
		class:noBackground
	*spellBoosttxt
		name:Spell boosts
		tag:spellBoosttxt
		text:Spell boosts
		desc:Things to make your spells better.
		class:noBackground
	*divinetxt
		name:Divine upgrades
		tag:divinetxt
		text:Divine upgrades[?(divineCups=0)|| - [divineCups] divine cups]
		desc:Powerful upgrades obtained by restarting.
		class:noBackground
	 icon:https://cdn.rawgit.com/morkysherk/b914a55433f5e3af3bab7b6d6641b29a/raw/15883d5279e720636ae9e91e83fdf33cd710055d/divinecup.svg
	*buildingtxt
		name:Buildings
		tag:buildingtxt
		text:Buildings - [this]
		desc:Buildings that produce resources.
		class:noBackground
		is always:(clickers+chocolateWorkers+refineries+chocoFarms+peanutButterers+pbFactories+factories+replicators+coreExtractors+qDownloaders+mindReaders+peanutCuppers+cupMachines+printers+cupVomiters+rearrangers+rocketShips+cupPortals+mysteryBoxes+subAtomics+bhExtractors+anomalies)
	*buy10
		no tooltip
		tag:bulkSellBuy
		text:[?(this=0)|Enable buying 10|Disable buying 10]
		passive:if (this=1) multiply cost of tag:philding by 20.303718238052734375
		on click:
			if (this=0) $this=1
			if (this=1) $this=0
			if ($this=1) this=1
			if ($this=0) this=0
			sell1=0
			sell1a=0
			buy50=0
			buy50a=0
			sell10=0
			sell10a=0
			sell50=0
			sell50a=0
		end
	*buy10a
		name:buoy 10
		tag:resource
		class:invisible
	*buy50
		no tooltip
		tag:bulkSellBuy
		text:[?(this=0)|Enable buying 50|Disable buying 50]
		passive:if (this=1) multiply cost of tag:philding by 7217.71627722638393616771145585305494136208417997711591070724277960177772683891816996037960052490234375
		on click:
			if (this=0) $this=1
			if (this=1) $this=0
			if ($this=1) this=1
			if ($this=0) this=0
			sell1=0
			sell1a=0
			buy10=0
			buy10a=0
			sell10=0
			sell10a=0
			sell50=0
			sell50a=0
		end
	*buy50a
		tag:resource
		class:invisible
	*sell1
		no tooltip
		tag:bulkSellBuy
		text:[?(this=0)|Enable selling|Disable selling]
		passive:
			if (this=1) multiply cost of tag:philding by -0.6
		end
		passive:
			if (angelicCuppers<1 and this=1) multiply cost of angelicCuppers by -1e308
			if (clickers<1 and this=1) multiply cost of clickers by -1e308
			if (chocolateWorkers<1 and this=1) multiply cost of chocolateWorkers by -1e308
			if (refineries<1 and this=1) multiply cost of refineries by -1e308
			if (chocoFarms<1 and this=1) multiply cost of chocoFarms by -1e308
			if (peanutButterers<1 and this=1) multiply cost of peanutButterers by -1e308
			if (pnConverters<1 and this=1) multiply cost of pnConverters by -1e308
			if (factories<1 and this=1) multiply cost of factories by -1e308
			if (replicators<1 and this=1) multiply cost of replicators by -1e308
			if (coreExtractors<1 and this=1) multiply cost of coreExtractors by -1e308
			if (qDownloaders<1 and this=1) multiply cost of qDownloaders by -1e308
			if (mindReaders<1 and this=1) multiply cost of mindReaders by -1e308
			if (peanutCuppers<1 and this=1) multiply cost of peanutCuppers by -1e308
			if (cupMachines<1 and this=1) multiply cost of cupMachines by -1e308
			if (printers<1 and this=1) multiply cost of printers by -1e308
			if (cupVomiters<1 and this=1) multiply cost of cupVomiters by -1e308
			if (rearrangers<1 and this=1) multiply cost of rearrangers by -1e308
			if (tradeShips<1 and this=1) multiply cost of tradeShips by -1e308
			if (cupPortals<1 and this=1) multiply cost of cupPortals by -1e308
			if (mysteryBoxes<1 and this=1) multiply cost of mysteryBoxes by -1e308
			if (subAtomics<1 and this=1) multiply cost of subAtomics by -1e308
			if (bhExtractors<1 and this=1) multiply cost of bhExtractors by -1e308
			if (anomalies<1 and this=1) multiply cost of anomalies by -1e308
		end
		on click:
			if (this=0) $this=1
			if (this=1) $this=0
			if ($this=1) this=1
			if ($this=0) this=0
			buy10=0
			buy10a=0
			buy50=0
			buy50a=0
			sell10=0
			sell10a=0
			sell50=0
			sell50a=0
		end
	*sell1a
		tag:resource
		class:invisible
	*sell10
		no tooltip
		tag:bulkSellBuy
		text:[?(this=0)|Enable selling 10|Disable selling 10]
		passive:if (this=1) multiply cost of tag:philding by -3.01126117549
		passive:
			if (angelicCuppers<10 and this=1) multiply cost of angelicCuppers by -1e308
			if (clickers<10 and this=1) multiply cost of clickers by -1e308
			if (chocolateWorkers<10 and this=1) multiply cost of chocolateWorkers by -1e308
			if (refineries<10 and this=1) multiply cost of refineries by -1e308
			if (chocoFarms<10 and this=1) multiply cost of chocoFarms by -1e308
			if (peanutButterers<10 and this=1) multiply cost of peanutButterers by -1e308
			if (pnConverters<10 and this=1) multiply cost of pnConverters by -1e308
			if (factories<10 and this=1) multiply cost of factories by -1e308
			if (replicators<10 and this=1) multiply cost of replicators by -1e308
			if (coreExtractors<10 and this=1) multiply cost of coreExtractors by -1e308
			if (qDownloaders<10 and this=1) multiply cost of qDownloaders by -1e308
			if (mindReaders<10 and this=1) multiply cost of mindReaders by -1e308
			if (peanutCuppers<10 and this=1) multiply cost of peanutCuppers by -1e308
			if (cupMachines<10 and this=1) multiply cost of cupMachines by -1e308
			if (printers<10 and this=1) multiply cost of printers by -1e308
			if (cupVomiters<10 and this=1) multiply cost of cupVomiters by -1e308
			if (rearrangers<10 and this=1) multiply cost of rearrangers by -1e308
			if (tradeShips<10 and this=1) multiply cost of tradeShips by -1e308
			if (cupPortals<10 and this=1) multiply cost of cupPortals by -1e308
			if (mysteryBoxes<10 and this=1) multiply cost of mysteryBoxes by -1e308
			if (subAtomics<10 and this=1) multiply cost of subAtomics by -1e308
			if (bhExtractors<10 and this=1) multiply cost of bhExtractors by -1e308
			if (anomalies<10 and this=1) multiply cost of anomalies by -1e308
		end
		on click:
			if (this=0) $this=1
			if (this=1) $this=0
			if ($this=1) this=1
			if ($this=0) this=0
			buy10=0
			buy10a=0
			buy50=0
			buy50a=0
			sell1=0
			sell1a=0
			sell50=0
			sell50a=0
		end
	*sell10a
		tag:resource
		class:invisible
	*sell50
		no tooltip
		tag:bulkSellBuy
		text:[?(this=0)|Enable selling 50|Disable selling 50]
		passive:if (this=1) multiply cost of tag:philding by -3.99630879658
		passive:
			if (angelicCuppers<50 and this=1) multiply cost of angelicCuppers by -1e308
			if (clickers<50 and this=1) multiply cost of clickers by -1e308
			if (chocolateWorkers<50 and this=1) multiply cost of chocolateWorkers by -1e308
			if (refineries<50 and this=1) multiply cost of refineries by -1e308
			if (chocoFarms<50 and this=1) multiply cost of chocoFarms by -1e308
			if (peanutButterers<50 and this=1) multiply cost of peanutButterers by -1e308
			if (pnConverters<50 and this=1) multiply cost of pnConverters by -1e308
			if (factories<50 and this=1) multiply cost of factories by -1e308
			if (replicators<50 and this=1) multiply cost of replicators by -1e308
			if (coreExtractors<50 and this=1) multiply cost of coreExtractors by -1e308
			if (qDownloaders<50 and this=1) multiply cost of qDownloaders by -1e308
			if (mindReaders<50 and this=1) multiply cost of mindReaders by -1e308
			if (peanutCuppers<50 and this=1) multiply cost of peanutCuppers by -1e308
			if (cupMachines<50 and this=1) multiply cost of cupMachines by -1e308
			if (printers<50 and this=1) multiply cost of printers by -1e308
			if (cupVomiters<50 and this=1) multiply cost of cupVomiters by -1e308
			if (rearrangers<50 and this=1) multiply cost of rearrangers by -1e308
			if (tradeShips<50 and this=1) multiply cost of tradeShips by -1e308
			if (cupPortals<50 and this=1) multiply cost of cupPortals by -1e308
			if (mysteryBoxes<50 and this=1) multiply cost of mysteryBoxes by -1e308
			if (subAtomics<50 and this=1) multiply cost of subAtomics by -1e308
			if (bhExtractors<50 and this=1) multiply cost of bhExtractors by -1e308
			if (anomalies<50 and this=1) multiply cost of anomalies by -1e308
		end
		on click:
			if (this=0) $this=1
			if (this=1) $this=0
			if ($this=1) this=1
			if ($this=0) this=0
			buy10=0
			buy10a=0
			buy50=0
			buy50a=0
			sell1=0
			sell1a=0
			sell10=0
			sell10a=0
		end
	*sell50a
		tag:resource
		class:invisible


	//GENERATED CODE DIGITS

	*debugDigit1
		tag:resource
	*debugDigit2
		tag:resource
	*debugDigit3
		tag:resource
	*debugDigit4
		tag:resource

	//BUTTONS

	*viewDebug
		name:Debug
		text:Debug
		on click:
			hide tag:spell
			hide tag:upgrade
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			hide tag:achievPoints
			hide tag:achievement
			dim tag:achievement
			dim tag:achievement:notOwned
			hide tag:secretPoints
			hide tag:secret
			hide tag:philding
			hide tag:stat
			hide tag:spelltxt
			hide upgradetxt
			hide tag:setting
			hide tag:settingTitle
			hide tag:buildingtxt
			hide tag:divinetxt
			hide tag:divine
			hide tag:spellBoosttxt
			hide tag:spellBoost
			show tag:debug
			hide tag:bulkSellBuy
		end
		tag:debugButton
		class:leftBorder rightBorder debugButton
	*viewSettings
		name:Settings
		text:Settings
		on click:
			hide tag:spell
			hide tag:upgrade
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			hide tag:achievPoints
			hide tag:achievement
			dim tag:achievement
			dim tag:achievement:notOwned
			hide tag:secretPoints
			hide tag:secret
			hide tag:philding
			hide tag:stat
			hide tag:spelltxt
			hide upgradetxt
			show tag:setting
			show tag:settingTitle
			hide tag:buildingtxt
			hide tag:divinetxt
			hide tag:divine
			hide tag:spellBoosttxt
			hide tag:spellBoost
			hide tag:debug
			hide tag:bulkSellBuy
		end
		tag:menuButton
		class:leftBorder
	*viewBuildings
		name:Buildings
		tag:menuButton
		text:Buildings
		desc:Buildings to produce more resources.
		on click:
			hide tag:spell
			hide tag:upgrade
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			hide tag:achievPoints
			hide tag:achievement
			dim tag:achievement
			dim tag:achievement:notOwned
			hide tag:secretPoints
			hide tag:secret
			show tag:philding
			hide tag:stat
			hide tag:spelltxt
			hide upgradetxt
			hide tag:setting
			hide tag:settingTitle
			show tag:buildingtxt
			hide tag:divinetxt
			hide tag:divine
			hide tag:spellBoosttxt
			hide tag:spellBoost
			hide tag:debug
			show tag:bulkSellBuy
		end
	*viewUpgrades
		name:Upgrades
		tag:menuButton
		text:Upgrades
		desc:Upgrades to give you boosts.
		on click:
			show tag:spell
			show :Upgrades
			hide tag:upgrade:owned
			show tag:ownedUpgradetxt
			show tag:upgradeOwned
			hide tag:achievPoints
			hide tag:achievement
			dim tag:achievement
			dim tag:achievement:notOwned
			hide tag:secretPoints
			hide tag:secret
			hide tag:philding
			hide tag:stat
			show tag:spelltxt
			show upgradetxt
			hide tag:setting
			hide tag:settingTitle
			hide tag:buildingtxt
			show tag:spellBoosttxt
			show tag:spellBoost
			if (peanutCups:earned>=1e12)
				show tag:divinetxt
				show tag:divine
			else
				hide tag:divine
			end
			hide tag:debug
			hide tag:bulkSellBuy
		end
	*viewAchievs
		name:Achievements
		tag:menuButton
		text:Achievements
		desc:Achievements and secrets.
		on click:
			hide tag:spell
			hide tag:upgrade
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			show tag:achievPoints
			show tag:achievement
			light tag:achievement
			light tag:achievement:notOwned
			show tag:secretPoints
			show tag:secret
			hide tag:philding
			hide tag:stat
			hide tag:spelltxt
			hide upgradetxt
			hide tag:setting
			hide tag:settingTitle
			hide tag:buildingtxt
			hide tag:divinetxt
			hide tag:divine
			hide tag:spellBoosttxt
			hide tag:spellBoost
			hide tag:debug
			hide tag:bulkSellBuy
		end
	*viewStats
		name:Stats
		tag:menuButton
		text:Stats
		desc:Statistics about your playthrough.
		on click:
			hide tag:spell
			hide tag:upgrade
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			hide tag:achievPoints
			hide tag:achievement
			dim tag:achievement
			dim tag:achievement:notOwned
			hide tag:secretPoints
			hide tag:secret
			hide tag:philding
			show tag:stat
			hide tag:spelltxt
			hide upgradetxt
			hide tag:setting
			hide tag:settingTitle
			hide tag:buildingtxt
			hide tag:divinetxt
			hide tag:divine
			hide tag:spellBoosttxt
			hide tag:spellBoost
			hide tag:debug
			hide tag:bulkSellBuy
		end
		class:rightBorder

	//SETTINGS

	*clickAnimation
		text:On click animation for upgrades, spells, achievements, and secrets:</>(You must save and refresh the game for this to work properly!)
		no tooltip
		tags:settingTitle csettingTitle
		class:noBackground lineBreak
	*clickWobble
		text:Wobble
		no tooltip
		on click:
			anim wobble
			clickAnimation is 1
		end
		tags:setting csetting
		class:cleared2
	*clickWobbleSlow
		text:Slow wobble
		no tooltip
		on click:
			anim wobbleSlow
			clickAnimation is 5
		end
		tags:setting csetting
	*clickBounce
		text:Bounce
		no tooltip
		on click:
			anim bounceOnce
			clickAnimation is 2
		end
		tags:setting csetting
	*clickPlop
		text:Plop
		no tooltip
		on click:
			anim plop
			clickAnimation is 3
		end
		tags:setting csetting
	*clickWiggle
		text:Wiggle
		no tooltip
		on click:
			anim wiggling
			clickAnimation is 4
		end
		tags:setting csetting
	*clickNone
		text:None
		no tooltip
		on click:
			clickAnimation is -1
		end
		tags:setting csetting
	*buttonAnimation
		text:On click animation for buttons:</>(You must save and refresh the game for this to work properly!)
		no tooltip
		tags:settingTitle bsettingTitle
		class:noBackground lineBreak
	*buttonWobble
		text:Wobble
		no tooltip
		on click:
			anim wobble
			buttonAnimation is 1
		end
		tags:setting bsetting
		class:cleared2
	*buttonWobbleSlow
		text:Slow wobble
		no tooltip
		on click:
			anim wobbleSlow
			buttonAnimation is 5
		end
		tags:setting bsetting
	*buttonBounce
		text:Bounce
		no tooltip
		on click:
			anim bounceOnce
			buttonAnimation is 2
		end
		tags:setting bsetting
	*buttonPlop
		text:Plop
		no tooltip
		on click:
			anim plop
			buttonAnimation is 3
		end
		tags:setting bsetting
	*buttonWiggle
		text:Wiggle
		no tooltip
		on click:
			anim wiggling
			buttonAnimation is 4
		end
		tags:setting bsetting
	*buttonNone
		text:None
		no tooltip
		on click:
			buttonAnimation is -1
		end
		tags:setting bsetting
	*cupRate
		name:Peanut butter cup production rate
		desc:Controls how quickly your peanut butter cup producers convert chocolate and peanut butter into cups. 0% stops production entirely, and 100% keeps production at full speed.
		text:Peanut butter cup production rate: [this]%
		on start:this=100
		on load:this=100
		tags:setting cupRateTitle
		class:noBackground
		passive:if (this>100) this=100
	*cupRate100
		text:+100%
		no tooltip
		on click:cupRate=100
		tags:setting cupRate
	*cupRate10
		text:+10%
		no tooltip
		on click:if (cupRate<90) yield 10 cupRate
		on click:if (cupRate>=90) cupRate=100
		tags:setting cupRate
	*cupRate1
		text:+1%
		no tooltip
		on click:if (cupRate<100) yield 1 cupRate
		tags:setting cupRate
	*cupRate100b
		text:-100%
		no tooltip
		on click:yield -100 cupRate
		tags:setting cupRate
	*cupRate10b
		text:-10%
		no tooltip
		on click:yield -10 cupRate
		tags:setting cupRate
	*cupRate1b
		text:-1%
		no tooltip
		on click:yield -1 cupRate
		tags:setting cupRate
	*code
		text:Code: [codeDigit1][codeDigit2][codeDigit3][codeDigit4]
		name:Codes
		desc:Codes can be found in secret descriptions, the forums, or the Discord server. Some are randomized and others are always the same. Redeem them here!
		tags:settingTitle codeTitle
		class:noBackground lineBreak
	*codeDigit1
		class:invisible
	*codeDigit2
		class:invisible
	*codeDigit3
		class:invisible
	*codeDigit4
		class:invisible
	*code1000
		text:+1000
		no tooltip
		on click:if (codeDigit1<9) yield 1 codeDigit1
		tags:setting code
	*code100
		text:+100
		no tooltip
		on click:if (codeDigit2<9) yield 1 codeDigit2
		tags:setting code
	*code10
		text:+10
		no tooltip
		on click:if (codeDigit3<9) yield 1 codeDigit3
		tags:setting code
	*code1
		text:+1
		no tooltip
		on click:if (codeDigit4<9) yield 1 codeDigit4
		tags:setting code
	*code1000b
		text:-1000
		no tooltip
		on click:yield -1 codeDigit1
		tags:setting code
	*code100b
		text:-100
		no tooltip
		on click:yield -1 codeDigit2
		tags:setting code
	*code10b
		text:-10
		no tooltip
		on click:yield -1 codeDigit3
		tags:setting code
	*code1b
		text:-1
		no tooltip
		on click:yield -1 codeDigit4
		tags:setting code
	*codeEnter
		text:Enter code
		no tooltip
		tags:setting code
		on click:
			if (codeDigit1=debugDigit1 and codeDigit2=debugDigit2 and codeDigit3=debugDigit3 and codeDigit4=debugDigit4)
				show tag:debugButton
				toast Unlocked the debug console! Warning: using any debug buttons counts as cheating and you will be labeled a cheater!
				yield hackerMan
			end
		end
		*upgrCheck
			tag:resource
			class:invisible

Shinies
	*luckyCup
		on click:
			if (no frenzyMultiplier)
				yield frenzyMultiplier	
			end
			yield 1 lclicks
		end
		on click:yield frandom(0,100) effectDeterminers
		on click:
			if (chance(0.00001%)) toast if you're reading this in-game, you're incredibly lucky
			$boost=1
			if (have blackcatHorseshoe) $boost=1.25
			if (have halfRainbow) $boost=1.5
			if (have closedUmbrella) $boost=1.75
			if (effectDeterminers<=25)
				$amount1=max(1,min(chocolate*0.25,(random(chocolate:ps*900,chocolate:ps*2700))))
				$amount2=max(1,min(peanutButter*0.25,(random(peanutButter:ps*900,peanutButter:ps*2700))))
				toast The golden peanut butter cup gave you [$amount1*$boost] chocolate bars and [$amount2*$boost] jars of peanut butter!
				yield ($amount1*$boost) chocolate
				yield ($amount2*$boost) peanutButter
				if (peanutCups:ps>=1)
					$amount3=min(peanutCups*0.2,random(peanutCups:ps*600,peanutCups:ps*1200))
					toast The golden peanut butter cup gave you [$amount3*$boost] peanut butter cups!
					yield ($amount3*$boost) peanutCups
				end
			end
			if (effectDeterminers>25 and effectDeterminers<=50)
				yield 45 frenzy
				toast The golden peanut butter cup is multiplying your production rate by 10 for 45 seconds!
			end
			if (effectDeterminers>50 and effectDeterminers<=70)
				$amount=(random(1,(min(100,goldBeans*0.01))))
				toast The golden peanut butter cup gave you [$amount*$boost] golden bean pod(s)!
				yield ($amount*$boost) goldBeanPods
			end
			if (effectDeterminers>70 and effectDeterminers<=88.5)
				$amount5=(random(1,3))
				toast The golden peanut butter cup permanently increased your chance of finding a golden bean pod when clicking a button!
				yield ($amount5*$boost) chanceIncreases
			end
			if (effectDeterminers>88.5 and effectDeterminers<=98.5)
				$amount6=(random(500,1250))
				yield ($amount6*$boost) mana
				toast The golden peanut butter cup gave you [$amount6*$boost] mana!
			end
			if (effectDeterminers>98.5 and effectDeterminers<=99.8)
				$amount4=(random(100,200))
				toast Wow! The golden peanut butter cup gave you [$amount4] golden bean pods!
				yield ($amount4) goldBeanPods
			end
			if (effectDeterminers>99.8 and effectDeterminers<=100)
				toast Golden cup storm!
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
			end
			if (effectDeterminers>100 and effectDeterminers<=125)
				$amount7=max(1,min(chocolate*0.5,(random(chocolate:ps*2700,chocolate:ps*5400))))
				$amount8=max(1,min(peanutButter*0.5,(random(peanutButter:ps*2700,peanutButter:ps*5400))))
				toast The golden peanut butter cup gave you [$amount7*$boost] chocolate bars and [$amount8*$boost] jars of peanut butter!
				yield ($amount7*$boost) chocolate
				yield ($amount8*$boost) peanutButter
				$amount9=min(peanutCups*0.5,random(peanutCups:ps*1500,peanutCups:ps*3000))
				toast The golden peanut butter cup gave you [$amount9*$boost] peanut butter cups!
				yield ($amount9*$boost) peanutCups
			end
			if (effectDeterminers>125 and effectDeterminers<=150)
				yield 45 frenzy2
				toast The golden peanut butter cup is multiplying your production rate by 25 for 45 seconds!
			end
			if (effectDeterminers>150 and effectDeterminers<=170)
				$amount10=(random(10,(min(250,goldBeans*0.03))))
				toast The golden peanut butter cup gave you [$amount10*$boost] golden bean pod(s)!
				yield ($amount10*$boost) goldBeanPods
			end
			if (effectDeterminers>170 and effectDeterminers<=188.5)
				$amount11=(random(3,6))
				toast The golden peanut butter cup permanently increased your chance of finding a golden bean pod when clicking a button!
				yield ($amount11*$boost) chanceIncreases
			end
			if (effectDeterminers>188.5 and effectDeterminers<=198.5)
				$amount12=(random(1000,2500))
				yield ($amount12*$boost) mana
				toast The golden peanut butter cup gave you [$amount12*$boost] mana!
			end
			if (effectDeterminers>198.5 and effectDeterminers<=199.5)
				$amount13=(random(300,600))
				toast Wow! The golden peanut butter cup gave you [$amount13] golden bean pods!
				yield ($amount4) goldBeanPods
			end
			if (effectDeterminers>199.5 and effectDeterminers<=200)
				toast Mega golden cup storm!
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
				spawn luckyCup
			end
			if (effectDeterminers>200)
				toast sorry nothing
			end
		frequency:400
		frequency variation:35
		icon:https://imgur.com/sAoosRq.png
		duration:15
		movement:growShrink onBox:shinyBox
		class:bigButton hasFlares
		end
	*goldPod
		movement:onTop moveBottom randomAngle
		frequency:100
		frequency variation:15
		class:bigButton classs
		duration:20
		icon:https://cdn.rawgit.com/morkysherk/3cac38333147cccd980e39f356f869ac/raw/c335d03212d9681ae2787531f90de28b4a3c218d/goldB2.svg
		on click:
			spawn goldBeanS
			spawn goldBeanS
			spawn goldBeanS
			spawn goldBeanS
			if (chance(75%)) spawn goldBeanS
			if (chance(50%)) spawn goldBeanS
			if (chance(25%)) spawn goldBeanS
			if (chance(12.5%)) spawn goldBeanS
			if (chance(6.75%)) spawn goldBeanS
			if (chance(3.375%)) spawn goldBeanS
			if (chance(1.6875%)) spawn goldBeanS
			toast Opened the falling golden bean pod!
		end
	*goldBeanS
		on click:
			if (have podSummonBoost and chance(10%))
				$cbeans=0.75*pow(1.1,summonBoost)
				$cbeans2=($cbeans+random((-($cbeans*0.1)),($cbeans*0.1)))
				yield $cbeans2 goldBeans
				toast You got [$cbeans2] crystal bean[?($cbeans2=1)||s]!
			else if (have podSummonBoost) 
				$beans=10*pow(1.1,summonBoost)
				$beans2=($beans+random((-($beans*0.1)),($beans*0.1)))
				yield $beans2 goldBeans
				toast You got [$beans2] golden bean[?($beans2=1)||s]!
			else
				$beans=(5+random(-1,1))
				yield $beans goldBeans
				toast You got [$beans] golden bean[?($beans=1)||s]!
			end
		end
	  icon:https://cdn.rawgit.com/morkysherk/0cb62044381cee43fa9deb2242c067cf/raw/938f6f8b7d570260fe0dde0cba17881a626e3eff/goldenB2.svg
		class:bigButton
		duration:3
		movement:onBox:shinyBox growShrink

Layout
	*main
		contains:res, cbuttons, pbuttons, res2, res3
  		*res
    		contains:tag:resource
    		class:fullWidth
		*res2
			contains:tag:special
			class:fullWidth
			ps:hide
		*res3
			contains:tag:timer
  		*cbuttons
			contains:tag:cButton
		*pbuttons
			contains:tag:pButton
		*coolBox
		*shinyBox

	*store
  		contains:store2, log, menuButtons, menuButtons2
		*log
			contains:Log
		*menuButtons
			contains:tag:menuButton
			no tooltip
		*menuButtons2
			contains:tag:debugButton
			no tooltip
		*codeButtons
			contains:tag:code
		*clickanimSettings
			contains:tag:csetting
		*buttonSettingTitle
			contains:tag:bsettingTitle
		*buttonSettings
			contains:tag:bsetting
		*cupRateButtons
			contains:tag:cupRate

 		*store2
   	 		contains:tag:warning, tag:csettingTitle, clickanimSettings, tag:bsettingTitle, buttonSettings, tag:cupRateTitle, cupRateButtons, tag:codeTitle, codeButtons, tag:buildingtxt, tag:bulkSellBuy, tag:philding, tag:upgradetxt, tag:upgrade, tag:ownedUpgradetxt, tag:upgradeOwned, tag:spelltxt, tag:spell, tag:spellBoosttxt, tag:spellBoost, tag:divinetxt, tag:divine, tag:achievPoints, tag:achievement, tag:secretPoints, tag:secret, tag:stat, tag:debug
    		tooltip origin:left
			ps:hide

Buildings
	*aaa|aaaa
		name:aaa|aaaa
		on tick:yield 1 secondPlayed
		on tick:yield 1 noClickSecond
		on tick:yield -1 frenzy
		on tick:if (peanutButter:ps<0) pwarning is 1
		on tick:if (peanutButter:ps>0) pwarning is 0
		on tick:if (pwarning=1) show pwarning
		on tick:if (pwarning=0) hide pwarning
		on tick:if (chocolate:ps<0) cwarning is 1
		on tick:if (chocolate:ps>0) cwarning is 0
		on tick:if (pwarning=1) show cwarning
		on tick:if (pwarning=0) hide cwarning
		on tick:if (aaa>1) aaa is 1
		on tick:yield -1 delay
		on tick:yield -1 frenzy2
		on tick:yield -100 effectDeterminers
		on tick:if (buy10=0) buy10a=0
		on tick:if (buy10=1) buy10a=1
		on tick:if (buy50=0) buy50a=0
		on tick:if (buy50=1) buy50a=1
		on tick:if (sell1=0) sell1a=0
		on tick:if (sell1=1) sell1a=1
		on tick:if (sell10=0) sell10a=0
		on tick:if (sell10=1) sell10a=1
		on tick:if (sell50=0) sell50a=0
		on tick:if (sell50=1) sell50a=1
		passive:multiply yield of tag:peanutCupper by (((((((((((0.01*cupRate)))))))))))
		class:invisible
		on start:
			log <#ffffff><b><u>Update Log</u></b></#></>     <//><#5dff44><i>Update 9 but it's the real one</i></#> - <#42bff4>April 2nd, 2018</#><.>Spell boosts<.>The very beginnings of a prestige system (shows up at 1T peanut butter cups earned)<.>4 new "tier 2" buildings<.>A purchased upgrades section<.>A couple new spells<.>A couple new golden bean upgrades<.>Renamed a building and made a new icon for another<.>svgs? uhhhhhhhhhhhhhhhhhhhhhhhhhhhhh maybe next update<.><i>Mini-updates:</i> Made it so the new buildings actually require prestige, as was originally intended. Also fixed the "Spawn golden peanut butter cup" spell</>     <//><#5dff44><i>Update 8</i></#> - <#42bff4>February 26th, 2018</#><.>Redone golden bean system<.>A few time-based achievements<.>Some achievement bonuses<.>A few more SVGs (oh god I still need to make more)<.>Slightly different layout with other small visual changes<.>Disabled multiplier stat (hopefully temporarily) because it wasn't working properly<.>A couple experimental log notifications, more may be added later<.>More colorful building descriptions<.>New secret-ish golden peanut butter cup effects<.><i>Mini-updates:</i> Fixed some bugs involving golden peanut butter cups</>     <//><#5dff44><i>Update 7</i></#> - <#42bff4>February 1st, 2018</#><.>New layout with tabs!<.>Loads of achievements<.>Spawn Lucky Peanut Butter Cup is hopefully bug-free now<.>More icons got the SVG treatment. The rest will come soon. Probably. Maybe. It's a possibility.</>     <//><#5dff44><i>Update 6</i></#> - <#42bff4>January 19th, 2018</#><.>A few icons were redrawn, either because they looked kinda bad or I lost the source file<.>Most of the game's icons are now SVGs<.>Some more achievements<.>A couple minor CSS changes<.><i>Mini-updates:</i> Fixed a few bugs affecting the "Spawn Golden Peanut Butter Cup" spell, and significantly improved game performance</>     <//><#5dff44><i>Update 5</i></#> - <#42bff4>January 1st, 2018</#><.>Lots of upgrades! Every building now has at least 4<.>A change to how golden peanut butter cup effects are chosen - this should make it easier to add more effects in the future<.>Stats look a bit better (in my opinion at least)<.>2 new better button upgrades and a significant buff to better button 5<#5dff44></>     <//><#5dff44><i>Update 4</i></#> - <#42bff4>December 2017</#><.>3 new buildings<.>More graphical changes<.>More balancing<.><i>Mini-updates:</i> A separate section for spells, and a more informative info screen</>     <//><#5dff44><i>Update 3</i></#> - <#42bff4>December 2017</#><.>Lots o' graphics<.>2 new buildings<.>More upgrades<.>With a side of rebalancing<.><i>Mini-updates:</i> More stuff to please your eyeballs</>     <//><#5dff44><i>Update 2</i></#> - <#42bff4>December 2017</#><.>2 new buildings<.>Lucky peanut butter cups now have a frenzy-like effect<.>2 new stats</>     <//><#5dff44><i>Update 1</i></#> - <#42bff4>December 2017</#><.>Some rebalancing<.>1 more achievement</>     <//><#5dff44><i>Release</i></#> - <#42bff4>December 2017</#><.>added plenty of stuff, removed a bit of stuff, changed some stuff, fixed a whole lot of stuff</>     <//><#5dff44><i>The Beginning</i></#> - <#42bff4>December 2nd, 2017</#><.>woah this Idle Game Maker thing looks neat<.>time to start makin' a game
			clickAnimation is 3
			hide tag:spell
			hide tag:upgrade
			hide tag:achievPoints
			hide tag:achievement
			dim :Achievements:notOwned
			hide tag:secretPoints
			hide tag:secret
			show :Buildings
			hide tag:stat
			hide upgradetxt
			hide tag:spelltxt
			hide tag:setting
			hide tag:settingTitle
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			hide tag:spellBoosttxt
			hide tag:spellBoost
			hide tag:divinetxt
			hide tag:divine
			hide tag:debugButton
			hide tag:debug
			yield random(0,9) debugDigit1
			yield random(0,9) debugDigit2
			yield random(0,9) debugDigit3
			yield random(0,9) debugDigit4
		end
		on start:log Welcome to Peanut Butter Cupper!
		on load:
			log <#ffffff><b><u>Update Log</u></b></#></>     <//><#5dff44><i>Update 9 but it's the real one</i></#> - <#42bff4>April 2nd, 2018</#><.>Spell boosts<.>The very beginnings of a prestige system (shows up at 1T peanut butter cups earned)<.>4 new "tier 2" buildings<.>A purchased upgrades section<.>A couple new spells<.>A couple new golden bean upgrades<.>Renamed a building and made a new icon for another<.>svgs? uhhhhhhhhhhhhhhhhhhhhhhhhhhhhh maybe next update<.><i>Mini-updates:</i> Made it so the new buildings actually require prestige, as was originally intended. Also fixed the "Spawn golden peanut butter cup" spell</>     <//><#5dff44><i>Update 8</i></#> - <#42bff4>February 26th, 2018</#><.>Redone golden bean system<.>A few time-based achievements<.>Some achievement bonuses<.>A few more SVGs (oh god I still need to make more)<.>Slightly different layout with other small visual changes<.>Disabled multiplier stat (hopefully temporarily) because it wasn't working properly<.>A couple experimental log notifications, more may be added later<.>More colorful building descriptions<.>New secret-ish golden peanut butter cup effects<.><i>Mini-updates:</i> Fixed some bugs involving golden peanut butter cups</>     <//><#5dff44><i>Update 7</i></#> - <#42bff4>February 1st, 2018</#><.>New layout with tabs!<.>Loads of achievements<.>Spawn Lucky Peanut Butter Cup is hopefully bug-free now<.>More icons got the SVG treatment. The rest will come soon. Probably. Maybe. It's a possibility.</>     <//><#5dff44><i>Update 6</i></#> - <#42bff4>January 19th, 2018</#><.>A few icons were redrawn, either because they looked kinda bad or I lost the source file<.>Most of the game's icons are now SVGs<.>Some more achievements<.>A couple minor CSS changes<.><i>Mini-updates:</i> Fixed a few bugs affecting the "Spawn Golden Peanut Butter Cup" spell, and significantly improved game performance</>     <//><#5dff44><i>Update 5</i></#> - <#42bff4>January 1st, 2018</#><.>Lots of upgrades! Every building now has at least 4<.>A change to how golden peanut butter cup effects are chosen - this should make it easier to add more effects in the future<.>Stats look a bit better (in my opinion at least)<.>2 new better button upgrades and a significant buff to better button 5<#5dff44></>     <//><#5dff44><i>Update 4</i></#> - <#42bff4>December 2017</#><.>3 new buildings<.>More graphical changes<.>More balancing<.><i>Mini-updates:</i> A separate section for spells, and a more informative info screen</>     <//><#5dff44><i>Update 3</i></#> - <#42bff4>December 2017</#><.>Lots o' graphics<.>2 new buildings<.>More upgrades<.>With a side of rebalancing<.><i>Mini-updates:</i> More stuff to please your eyeballs</>     <//><#5dff44><i>Update 2</i></#> - <#42bff4>December 2017</#><.>2 new buildings<.>Lucky peanut butter cups now have a frenzy-like effect<.>2 new stats</>     <//><#5dff44><i>Update 1</i></#> - <#42bff4>December 2017</#><.>Some rebalancing<.>1 more achievement</>     <//><#5dff44><i>Release</i></#> - <#42bff4>December 2017</#><.>added plenty of stuff, removed a bit of stuff, changed some stuff, fixed a whole lot of stuff</>     <//><#5dff44><i>The Beginning</i></#> - <#42bff4>December 2nd, 2017</#><.>woah this Idle Game Maker thing looks neat<.>time to start makin' a game
			hide tag:spell
			hide tag:upgrade
			hide tag:achievPoints
			hide tag:achievement
			dim :Achievements:notOwned
			hide tag:secretPoints
			hide tag:secret
			show :Buildings
			hide tag:stat
			hide upgradetxt
			hide tag:spelltxt
			hide tag:setting
			hide tag:settingTitle
			hide tag:ownedUpgradetxt
			hide tag:upgradeOwned
			hide tag:spellBoosttxt
			hide tag:spellBoost
			hide tag:divinetxt
			hide tag:divine
			hide tag:debugButton
			hide tag:debug
			if (debugDigit1=0 and debugDigit2=0 and debugDigit3=0 and debugDigit4=0)
				yield random(0,9) debugDigit1
				yield random(0,9) debugDigit2
				yield random(0,9) debugDigit3
				yield random(0,9) debugDigit4
			end
			if (achievPoints=0)
				if (have itBegins) yield 1 achievPoint
				if (have upandCup) yield 1 achievPoint
				if (have eatemUp) yield 1 achievPoint
				if (have pbchocolateFlavor) yield 1 achievPoint
				if (have peanutbuttercupHead) yield 1 achievPoint
				if (have massProduce) yield 1 achievPoint
				if (have aLot) yield 1 achievPoint
				if (have plenty) yield 1 achievPoint
				if (have lifeSupply) yield 1 achievPoint
				if (have Surplus) yield 1 achievPoint
				if (have hired) yield 1 achievPoint
				if (have hardlyWorking) yield 1 achievPoint
				if (have workingHard) yield 1 achievPoint
				if (have peanutButtered) yield 1 achievPoint
				if (have peanutbutterCupped) yield 1 achievPoint
				if (have automated) yield 1 achievPoint
				if (have futureisNow) yield 1 achievPoint
				if (have makingArrangements) yield 1 achievPoint
				if (have cupsinSpace) yield 1 achievPoint
				if (have notaButton) yield 1 achievPoint
				if (have stop) yield 1 achievPoint
				if (have whyThough) yield 1 achievPoint
				if (clickAnimation=0) clickAnimation is 3
			end
		end
		on load:
			if (secretPoints=0)
				if (have notaButton)
					yield 1 secretPoint
					yield -1 achievPoint
				end
				if (have stop)
					yield 1 secretPoint
					yield -1 achievPoint
				end
				if (have whyThough)
					yield 1 secretPoint
					yield -1 achievPoint
				end
				if (have specificAchiev)
					yield 1 secretPoint
				end
			end
		end
		on load:upgrCheck=ownedUpgradetxt
		start with:1
		on load:log Welcome back to Peanut Butter Cupper!

	//SPELL BOOSTS

	*manaBoost
		name:Mana boost
		desc:<.>Boosts your mana production by <b>1.5%</b> per level.<.>Stacks multiplicatively.<.>Current level: <b>[this]</b>
		cost:1 crystalBean
		cost:100 goldBeans
		class:smallThing spellBoost
		icon:numbers[0,0] https://cdn.rawgit.com/morkysherk/17878b0e6065cc04058debceaf423fb1/raw/183cf6fec09208f552ff4b4ed2dd3f58d00d4468/mana%20hat.svg
		tags:beanUpgrade spellBoost
		no text
		cost increase:113.5%
	*tallerHats
		name:Taller hats
		desc:<.>Boosts your mana capacity by <b>1%</b> per level.<.>Stacks multiplicatively.<.>Current level: <b>[this]</b>
		cost:1 crystalBean
		cost:100 goldBeans
		class:smallThing spellBoost
		icon:numbers[0,0] https://cdn.rawgit.com/morkysherk/17878b0e6065cc04058debceaf423fb1/raw/183cf6fec09208f552ff4b4ed2dd3f58d00d4468/mana%20hat.svg
		tags:beanUpgrade spellBoost
		no text
		cost increase:113.5%
	*brittleShells
		name:Brittle shells
		desc:<.>Golden bean pods require <b>1.5%</b> less mana to open per level.<.>Stacks multiplicatively.<.>Current level: <b>[this]</b>
		cost:1 crystalBean
		cost:100 goldBeans
		class:smallThing spellBoost
		tags:beanUpgrade spellBoost
		cost increase:112.5%
	  icon:numbers[0,0] https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
		no text
		cost increase:115%
	*summonBoost
		name:Golden bean pod summoning boost
		desc:<.>Summon <b>10%</b> more golden beans per spell cast.<.>Stacks multiplicatively.<.>Current level: <b>[this]</b>
		cost:10 crystalBean
		cost:1000 goldBeans
		class:smallThing spellBoost
		tags:beanUpgrade spellBoost
	  icon:numbers[0,0] https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
		no text
		cost increase:114.5%

	//BUILDINGS

	*manaThing|manaThings
		name:Mana Thing|Mana Things
		on tick:
			if (mana<(500*pow(1.01,tallerHats))) yield pow(1.0125,manaBoost) mana
		end
		start with:1
		class:invisible
	*angelicCupper|angelicCuppers
		name:Angelic Cupper|Angelic Cuppers
		desc:<.>Each angelic cupper increases your multiplier by <b>0.02%</b> per divine cup earned.<.>This boost stacks multiplicatively.
	 icon:https://cdn.rawgit.com/morkysherk/b914a55433f5e3af3bab7b6d6641b29a/raw/15883d5279e720636ae9e91e83fdf33cd710055d/divinecup.svg
		cost:10 peanutCups
		cost increase:200%
		class:cleared bigThing
		req:angelicCuppersUnlock
		on earn:if (buy10a=1) this=(this+9)
		on earn:if (buy50a=1) this=(this+49)
		on earn:if (sell1a=1) this=(this-2)
		on earn:if (sell10a=1) this=(this-11)
		on earn:if (sell50a=1) this=(this-51)
		tag:philding
	*clicker|clickers
		name:Autoclicker|Autoclickers
		desc:Clicks the buttons every 10 seconds.<//><i>Base effects:</i><.>Produces <b>1</b> bar of chocolate and jar of peanut butter every <b><#77ff72>10</#></b> seconds.<.>Affected by most button upgrades, but not production multipliers.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[(((clickerp:ps)/clickers)*10)]</#></b> bar(s) of chocolate every 10 seconds.
		cost:15 chocolate
		cost:15 peanutButter
		on tick:yield 0.1 chocolate
		on tick:yield 0.1 peanutButter
		on tick:yield 0.1 clickerp
		on tick:if (chance(min(2,(0.03+(chanceIncreases*0.003)))%)) yield 1 goldBeanPod
		on tick:if (have peanutcupClicking) yield (1/30) peanutCups
		icon:https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		class:cleared bigThing
		on earn:if (buy10a=1) this=(this+9)
		on earn:if (buy50a=1) this=(this+49)
		on earn:if (sell1a=1) this=(this-2)
		on earn:if (sell10a=1) this=(this-11)
		on earn:if (sell50a=1) this=(this-51)
		tag:philding
	*TEMPLATE
		tags:building philding
		class:bigThing
		on earn:if (buy10a=1) this=(this+9)
		on earn:if (buy50a=1) this=(this+49)
		on earn:if (sell1a=1) this=(this-2)
		on earn:if (sell10a=1) this=(this-11)
		on earn:if (sell50a=1) this=(this-51)

	//CHOCOLATE PRODUCERS

     *chocolateWorker|chocolateWorkers
          name:Chocolate Worker|Chocolate Workers
          desc:A worker to help you start producing chocolate.<//><i>Base effects:</i><.>Produces <b><#77ff72>1</#></b> bar of chocolate every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((chocoworkerp:ps)/chocolateWorkers)]</#></b> bar(s) of chocolate every second.
          cost:50 chocolate
          on tick:yield 1 chocolate
		  on tick:yield 1 chocoworkerp
		 icon:https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
		  on earn:if (chocolateWorkers=1) log(unlock) Upgrade unlocked - <b>Faster roasting</b>
		  on earn:if (chocolateWorkers=25) log(unlock) Upgrade unlocked - <b>Literal chocolate workers</b>
	*refinery|refineries
		name:Chocolate Farm|Chocolate Farms
		desc:Grows chocolate trees, the next evolution of cocoa trees.<//><i>Base effects:</i><.>Produces <b><#77ff72>10</#></b> bars of chocolate every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((chocofarmp:ps)/refineries)]</#></b> bars of chocolate every second.
		cost:750 chocolate
		on tick:yield 10 chocolate
		on tick:yield 10 chocofarmp
		req:330 cEarnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocoFarm|chocoFarms
		name:Chocolate Refinery|Chocolate Refineries
		desc:A refinery to produce large amounts of chocolate.<//><i>Base effects:</i><.>Produces <b><#77ff72>100</#></b> bars of chocolate every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((refineryp:ps)/chocoFarms)]</#></b> bars of chocolate every second.
		icon:https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		cost:11250 chocolate
		on tick:yield 100 chocolate
		req:6600 cEarnedThisUniverse
		on tick:yield 100 refineryp
	
	//PEANUT BUTTERERS
		
	*peanutButterer|peanutButterers
		name:Peanut Butterer|Peanut Butterers
		desc:A worker to help you start buttering peanuts.<//><i>Base effects:</i><.>Produces <b><#77ff72>1</#></b> jar of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((buttererp:ps)/peanutButterers)]</#></b> jars of peanut butter every second.
        cost:50 peanutButter
		on tick:yield 1 peanutButter
		on tick:yield 1 buttererp
		icon:https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*pbFactory|pbFactories|pnConverter|pnConverters
		name:Peas and Nuts Converter|Peas and Nuts Converters
		desc:Converts peas and nuts into peanut butter.<//><i>Base effects:</i><.>Produces <b><#77ff72>10</#></b> jars of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((converterp:ps)/pbFactories)]</#></b> jars of peanut butter every second.
		cost:750 peanutButter
		on tick:yield 10 peanutButter
		on tick:yield 10 converterp
		req:330 pEarnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*factory|factories
		name:Peanut Butter Factory|Peanut Butter Factories
		desc:A factory to produce peanut butter in bulk quantities.<//><i>Base effects:</i><.>Produces <b><#77ff72>100</#></b> jars of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((factoryp:ps)/factories)]</#></b> jars of peanut butter every second.
		cost:11250 peanutButter
		on tick:yield 100 peanutButter
		on tick:yield 100 factoryp
		req:6600 pEarnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
		icon class:leftRight

	//BOTH

	*replicator|replicators
		name:Replicator|Replicators
		desc:Duplicates chocolate and peanut butter.<//><.><i>Base effects:</i><.>Produces <b><#77ff72>1000</#></b> bars of chocolate and jars of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((replicatorp:ps)/replicators)]</#></b> bars of chocolate and jars of peanut butter every second.
		cost:168750 chocolate
		cost:168750 peanutButter
		on tick:yield 1000 chocolate
		on tick:yield 1000 peanutButter
		on tick:yield 1000 replicatorp
		req:80000 cEarnedThisUniverse
		req:80000 pEarnedThisUniverse
	icon:https://cdn.rawgit.com/morkysherk/52ab77aa07ae52a02994ad81c32e93f3/raw/3f64bc9762ac1154994d513193bf03f68aa41ba6/replicator.svg
	*coreExtractor|coreExtractors
		name:Core Extractor|Core Extractors
		desc:Extracts hot peanut butter and molten chocolate from the planet's core.<.><i>Base effects:</i><.>Produces <b><#77ff72>10000</#></b> bars of chocolate and jars of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((coreExtractorp:ps)/coreExtractors)]</#></b> bars of chocolate and jars of peanut butter every second.
		on tick:
			yield 10000 chocolate
			yield 10000 peanutButter
			yield 10000 coreExtractorp
		end
		cost:2700000 chocolate
		cost:2700000 peanutButter
		req:1300000 cEarnedThisUniverse
		req:1300000 pEarnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
	*qDownloader|qDownloaders
		name:Quantum Downloader|Quantum Downloaders
		desc:Maybe you wouldn't download a car, but you'd certainly download some peanut butter and chocolate.<.><i>Base effects:</i><.>Produces <b><#77ff72>200000</#></b> bars of chocolate and jars of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((qDownloaderp:ps)/qDownloaders)]</#></b> bars of chocolate and jars of peanut butter every second.
		on tick:
			yield 200000 chocolate
			yield 200000 peanutButter
			yield 200000 qDownloaderp
		end
		cost:80000000 chocolate
		cost:80000000 peanutButter
		req:35000000 cEarnedThisUniverse
		req:35000000 pEarnedThisUniverse
		req:prestige1
		icon:https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*mindReader|mindReaders
		name:Mind Reader|Mind Readers
		desc:Makes thoughts of peanut butter and chocolate a reality.<.><i>Base effects:</i><.>Produces <b><#77ff72>400000</#></b> bars of chocolate and jars of peanut butter every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((mindReaderp:ps)/mindReaders)]</#></b> bars of chocolate and jars of peanut butter every second.
		on tick:
			yield 4000000 chocolate
			yield 4000000 peanutButter
			yield 4000000 mindReaderp
		end
		cost:2560000000 chocolate
		cost:2560000000 peanutButter
		req:900000000 cEarnedThisUniverse
		req:900000000 pEarnedThisUniverse
		req:prestige1
		icon:https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg

	//PEANUT CUPPERS

	*TEMPLATE
		tags:building peanutCupper philding
		class:bigThing
		req:cupRecipe
		on earn:if (buy10a=1) this=(this+9)
		on earn:if (buy50a=1) this=(this+49)
		on earn:if (sell1a=1) this=(this-2)
		on earn:if (sell10a=1) this=(this-11)
		on earn:if (sell50a=1) this=(this-51)

	*peanutCupper|peanutCuppers
		name:Peanut Butter Cupper|Peanut Butter Cuppers
		desc: A worker to help you start cupping peanut butter.<//><i>Base effects:</i><.>Uses <b><#ff4444>1</#></b> bar of chocolate and jar of peanut butter every 2 seconds.<.>Produces <b><#77ff72>1</#></b> peanut butter cup every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[(((cupperuse:ps)/peanutCuppers)*2)]</#></b> bar(s) of chocolate and jar(s) of peanut butter every 2 seconds.<.>Produces about <b><#77ff72>[((cupperp:ps)/peanutCuppers)]</#></b> peanut butter cup(s) every second.
		cost:100 chocolate
		cost:100 peanutButter
		req:100 cEarnedThisUniverse
		req:100 pEarnedThisUniverse
		on tick:
			if (chocolate>0 and peanutButter>0) 
				yield 1 peanutCup
				yield -0.5 chocolate
				yield -0.5 peanutButter
				yield 1 cupperp
				yield 0.5 cupperuse
			end
		end
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*cupMachine|cupMachines
		name:Peanut Butter Cup Machine|Peanut Butter Cup Machines
		desc:A machine to help you start taking the peanut cuppers' jobs.<//><i>Base effects:</i><.>Uses <b><#ff4444>5</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>10</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[(((machineuse:ps)/cupMachines))]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((machinep:ps)/cupMachines)]</#></b> peanut butter cups every second.
	    cost:1500 peanutCups
		on tick:
			if (chocolate>0 and peanutButter>0) 
				yield 10 peanutCups
				yield -5 chocolate
				yield -5 peanutButter
			end
		end
		on tick:				
			yield 10 machinep
			yield 5 machineuse
		end
		req:500 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*printer|printers
		name:3D Printer|3D Printers
		desc:Prints out peanut butter cups.<//>Base effects:<.>Uses <b><#ff4444>30</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>60</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((printeruse:ps)/printers)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((printerp:ps)/printers)]</#></b> peanut butter cups every second.
		on tick:if (chocolate>0 and peanutButter>0) yield -30 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -30 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 60 peanutCups
		on tick:yield 30 printeruse
		on tick:yield 60 printerp
		cost:17500 peanutCups
		req:5000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
	*cupVomiter|cupVomiters
		name:Cup Puker|Cup Pukers
		desc:A cute little creature that eats peanut butter and chocolate and throws up peanut butter cups. Yes, they're safe to eat.<//>Base effects:<.>Uses <b><#ff4444>125</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>300</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((pukeruse:ps)/cupVomiters)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((pukerp:ps)/cupVomiters)]</#></b> peanut butter cups every second.
		on tick:
			if (chocolate>0 and peanutButter>0) 
				yield 300 peanutCups
				yield -125 chocolate
				yield -125 peanutButter
			end
		end
		on tick:yield 125 pukeruse
		on tick:yield 300 pukerp
		cost:200000 peanutCups
		req:65000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
	*rearranger|rearrangers
		name:Molecular Rearranger|Molecular Rearrangers
		desc:This amazing device combines chocolate and peanut butter at incredible rates.<//>Base effects:<.>Uses <b><#ff4444>750</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>1,750</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((rearrangeruse:ps)/rearrangers)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((rearrangerp:ps)/rearranger)]</#></b> peanut butter cups every second.
		on tick:if (chocolate>0 and peanutButter>0) yield -750 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -750 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 1750 peanutCups
		on tick:yield 750 rearrangeruse
		on tick:yield 1750 rearrangerp
		cost:2500000 peanutCups
		req:800000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*rocketShip|rocketShips|tradeShip|tradeShips
		name:Trade Spaceships
		desc:Trade with alien races across the universe.<//>Base effects:<.>Uses <b><#ff4444>4,000</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>10,000</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((rocketuse:ps)/rocketShips)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((rocketp:ps)/rocketShips)]</#></b> peanut butter cups every second.
		on tick:if (chocolate>0 and peanutButter>0) yield -4000 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -4000 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 10000 peanutCups
		on tick:yield 4000 rocketuse
		on tick:yield 10000 rocketp
		cost:30000000 peanutCups
		req:10000000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*cupPortal|cupPortals
		name:Portal|Portals
		desc:Send your chocolate and peanut butter to another dimension, where they are converted to peanut butter cups.<//>Base effects:<.>Uses <b><#ff4444>25,000</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>60,000</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((portaluse:ps)/cupPortals)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((portalp:ps)/cupPortals)]</#></b> peanut butter cups every second.
		on tick:if (chocolate>0 and peanutButter>0) yield -25000 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -25000 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 60000 peanutCups
		on tick:yield 25000 portaluse
		on tick:yield 60000 portalp
		cost:325000000 peanutCups
		req:100000000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*mysteryBox|mysteryBoxes
		name:Mystery Box|Mystery Boxes
		desc:A big magical box that sucks in peanut butter and chocolate and does... something that nobody's ever been able to observe. Whatever happens, peanut butter cups will probably come out.<//>Base effects:<.>Uses <b><#ff4444>125,000</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>325,000</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((mysteryuse:ps)/mysteryBoxes)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((mysteryp:ps)/mysteryBoxes)]</#></b> peanut butter cups every second.
		on tick:if (chocolate>0 and peanutButter>0) yield -125000 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -125000 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 325000 peanutCups
		on tick:yield 125000 mysteryuse
		on tick:yield 325000 mysteryp
		cost:3500000000 peanutCups
		req:100000000 earnedThisUniverse
	   icon:https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*subAtomic|subAtomics
		name:Subatomic moleculizer of the Greek bose-stein convapitators|Subatomic moleculizers of the Greek bose-stein convapitators
		desc:Whatever this is, it makes a heck of a lot of peanut butter cups without even using up chocolate or peanut butter.<//>Base effects:<.>Produces <b><#77ff72>1.35M</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Produces about <b><#77ff72>[((subatomicp:ps)/subAtomics)]</#></b> peanut butter cups every second.
		cost:40000000000 peanutCups
		req:10000000000 earnedThisUniverse
		on tick:yield 1350000 peanutCups
		on tick:yield 1350000 subatomicp
		icon:https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*bhExtractor|bhExtractors
		name:Black Hole Extractor|Black Hole Extractors
		desc:Throw your peanut butter and chocolate in the hole and extract it in the form of peanut butter cups.<//>Base effects:<.>Uses <b><#ff4444>3.5M</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>10M</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((bhExtractoruse:ps)/bhExtractors)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((bhExtractorp:ps)/bhExtractors)]</#></b> peanut butter cups every second.
		cost:678901234567 peanutCups
		req:150000000000 earnedThisUniverse
		req:prestige1
		on tick:if (chocolate>0 and peanutButter>0) yield -3500000 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -3500000 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 10000000 peanutCups
		on tick:yield 3500000 bhExtractoruse
		on tick:yield 10000000 bhExtractorp
		icon:https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*anomaly|anomalies
		name:Space-time Anomaly|Space-time Anomalies
		desc:Spontaneously and efficiently converts random bars of chocolate and jars of peanut butter into peanut butter cups while nobody's looking.<//>Base effects:<.>Uses <b><#ff4444>22.5M</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces <b><#77ff72>72.5M</#></b> peanut butter cups every second.<//><i>Current effects:</i><.>Uses about <b><#ff4444>[((anomalyuse:ps)/anomalies)]</#></b> bars of chocolate and jars of peanut butter every second.<.>Produces about <b><#77ff72>[((anomalyp:ps)/anomalies)]</#></b> peanut butter cups every second.
		cost:11500000000000 peanutCups
		req:3000000000000 earnedThisUniverse
		req:prestige1
		on tick:if (chocolate>0 and peanutButter>0) yield -22500000 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -22500000 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 72500000 peanutCups
		on tick:yield 22500000 anomalyuse
		on tick:yield 72500000 anomalyp
	   icon:https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*pConverter|pConverters
		name:Planet Converter|Planet Converters
		desc:Convert entire planets into peanut butter cups.<//>Base effects:<.>Uses <b>4,000,000</b> bars of chocolate and jars of peanut butter every second.<.>Produces <b>12,500,000</b> peanut butter cups every second.
		cost:500000000000 peanutCups
		req:100000000000 earnedThisUniverse
		on tick:if (chocolate>0 and peanutButter>0) yield -4000000 chocolate
		on tick:if (chocolate>0 and peanutButter>0) yield -4000000 peanutButter
		on tick:if (chocolate>0 and peanutButter>0) yield 12500000 peanutCups
		icon:https://imgur.com/lcD5XFA.png
		class:invisible
		
Upgrades
//upgrades section upgrade section (this is for easy ctrl+f searching)

	*TEMPLATE
		class:smallThing thing
		on click:
			if (clickAnimation=1)
				anim icon wobble2
				anim wobble2
			end
			if (clickAnimation=2)
				anim icon bounceOnce
				anim bounceOnce
			end
			if (clickAnimation=3)
				anim icon plop
				anim plop
			end
			if (clickAnimation=4)
				anim icon wiggling2
				anim wiggling
			end
			if (clickAnimation=5)
				anim icon wobbleSlow
				anim wobbleSlow
			end
		end
		no text
	*frenzyMultiplier
		name:frenzy multiplier
		class:invisible
		on tick:if (frenzy>0) multiply yield of tag:building by 10
		on tick:if (frenzy2>0) multiply yield of tag:building by 25
		owned

	//SPELLS

	*spawnLucky
        name:Spawn golden peanut butter cup
        no buy
        icon:hat[0,0] https://imgur.com/vbbkKUY.png
        on click:
            $cost=300
            if (have fourcloverLeaf) $cost=290
            if (have fourcloverLeaf and blackcatHorseshoe) $cost=275
            if (have fourcloverLeaf and blackcatHorseshoe and halfRainbow) $cost=260
			if (have fourcloverLeaf and blackcatHorseshoe and halfRainbow and closedUmbrella) $cost=245
			if (have fourcloverLeaf and blackcatHorseshoe and halfRainbow and closedUmbrella and d7) $cost=230
            if (delay=0)
	            if (mana>=$cost and chance(85%))
	                yield -$cost mana
					spawn luckyCup
	                toast You summoned a golden peanut butter cup!
					yield 35 delay
	            else if (mana>=$cost)
	                yield -$cost mana
	                toast Failed to summon a golden peanut butter cup.
					yield 35 delay
				else if (mana<$cost)
					toast Not enough mana!
				else
					toast hello! (if you see this in-game it's a bug)
				end
			else
				toast Wait for spell delay to wear off.
			end
		end
        desc:Spawn a golden peanut butter cup with <b>300</b> mana, most of the time. Must recharge for <b>35</b> seconds.
        tag:spell

	*reroll
		name:Reroll
		desc:<.>Replaces one random building with one other random building for <b>300</b> mana.<.>Will fail to reroll and use no mana if you don't own at least one of both the selected buildings.
		icon:https://cdn.rawgit.com/morkysherk/07ecde967da70808e668f73ccb77dfc4/raw/8032e741ca30d2851c7e62fad15d7209f4c6f42e/dice.svg
		tag:spell
		no buy
		on click:
			$roll1=random(1,18)
			if ($roll1=1)
				if (clickers>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=2)
				if (chocolateWorker>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=3)
				if (refineries>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=4)
				if (chocoFarms>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=5)
				if (peanutButterers>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=6)
				if (pnConverters>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=7)
				if (factories>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=8)
				if (replicators>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=9)
				if (coreExtractors>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=10)
				if (peanutCuppers>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=11)
				if (cupMachines>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=12)
				if (printers>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=13)
				if (cupVomiters>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=14)
				if (rearrangers>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=15)
				if (rocketShips>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=16)
				if (cupPortals>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=17)
				if (mysteryBoxes>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			if ($roll1=18)
				if (subAtomics>=1)
					$success1=1
				else
					toast Failed to reroll - no mana was used
					$success1=0
				end
			end
			$roll2=random(1,18)
			if ($roll2=1)
				if (clickers>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=2)
				if (chocolateWorker>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=3)
				if (refineries>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=4)
				if (chocoFarms>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=5)
				if (peanutButterers>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=6)
				if (pnConverters>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=7)
				if (factories>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=8)
				if (replicators>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=9)
				if (coreExtractors>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=10)
				if (peanutCuppers>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=11)
				if (cupMachines>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=12)
				if (printers>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=13)
				if (cupVomiters>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=14)
				if (rearrangers>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=15)
				if (rocketShips>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=16)
				if (cupPortals>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=17)
				if (mysteryBoxes>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($roll2=18)
				if (subAtomics>=1)
					$success2=1
				else
					toast Failed to reroll - no mana was used
					$success2=0
				end
			end
			if ($success1=1 and $success2=1 and mana>=300)
				yield -300 mana
				if ($roll1=1)
					yield -1 clicker
					toast Lost one autoclicker.
				end
				if ($roll1=2)
					yield -1 chocolateWorker
					toast Lost one chocolate worker.
				end
				if ($roll1=3)
					yield -1 refinery
					toast Lost one chocolate farm.
				end
				if ($roll1=4)
					yield -1 chocoFarm
					toast Lost one refinery.
				end
				if ($roll1=5)
					yield -1 peanutButterer
					toast Lost one peanut butterer.
				end
				if ($roll1=6)
					yield -1 pnConverter
					toast Lost one peas and nuts converter.
				end
				if ($roll1=7)
					yield -1 factory
					toast Lost one factory.
				end
				if ($roll1=8)
					yield -1 replicator
					toast Lost one replicator.
				end
				if ($roll1=9)
					yield -1 coreExtractor
					toast Lost one core extractor.
				end
				if ($roll1=10)
					yield -1 peanutCupper
					toast Lost one peanut butter cupper.
				end
				if ($roll1=11)
					yield -1 cupMachine
					toast Lost one peanut butter cup machine.
				end
				if ($roll1=12)
					yield -1 printer
					toast Lost one 3D printer.
				end
				if ($roll1=13)
					yield -1 cupVomiter
					toast Lost one puker.
				end
				if ($roll1=14)
					yield -1 rearranger
					toast Lost one molecular rearranger.
				end
				if ($roll1=15)
					yield -1 rocketShip
					toast Lost one rocketship.
				end
				if ($roll1=16)
					yield -1 cupPortal
					toast Lost one portal.
				end
				if ($roll1=17)
					yield -1 mysteryBox
					toast Lost one mystery box.
				end
				if ($roll1=18)
					yield -1 subAtomic
					toast Lost one subatomic moleculizer of the Greek bose-stein convapitators.
				end
				if ($roll2=1)
					yield 1 clicker
					toast Gained one autoclicker.
				end
				if ($roll2=2)
					yield 1 chocolateWorker
					toast Gained one chocolate worker.
				end
				if ($roll2=3)
					yield 1 refinery
					toast Gained one chocolate farm.
				end
				if ($roll2=4)
					yield 1 chocoFarm
					toast Gained one refinery.
				end
				if ($roll2=5)
					yield 1 peanutButterer
					toast Gained one peanut butterer.
				end
				if ($roll2=6)
					yield 1 pnConverter
					toast Gained one peas and nuts converter.
				end
				if ($roll2=7)
					yield 1 factory
					toast Gained one factory.
				end
				if ($roll2=8)
					yield 1 replicator
					toast Gained one replicator.
				end
				if ($roll2=9)
					yield 1 coreExtractor
					toast Gained one core extractor.
				end
				if ($roll2=10)
					yield 1 peanutCupper
					toast Gained one peanut butter cupper.
				end
				if ($roll2=11)
					yield 1 cupMachine
					toast Gained one peanut butter cup machine.
				end
				if ($roll2=12)
					yield 1 printer
					toast Gained one 3D printer.
				end
				if ($roll2=13)
					yield 1 cupVomiter
					toast Gained one puker.
				end
				if ($roll2=14)
					yield 1 rearranger
					toast Gained one molecular rearranger.
				end
				if ($roll2=15)
					yield 1 rocketShip
					toast Gained one rocketship.
				end
				if ($roll2=16)
					yield 1 cupPortal
					toast Gained one portal.
				end
				if ($roll2=17)
					yield 1 mysteryBox
					toast Gained one mystery box.
				end
				if ($roll2=18)
					yield 1 subAtomic
					toast Gained one subatomic moleculizer of the Greek bose-stein convapitators.
				end
			else if ($success1=1 and $success2=1)
				toast Not enough mana.
			end
		end

	*spawnBean
		name:Spawn golden bean pod
		desc:Spawn a golden bean pod with <b>50</b> mana, most of the time
		icon:hat[0,0] https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
		no buy
		on click:if (mana>=50) yield -50 mana
		tag:spell
		on click:
			if (mana>=50)
				if (chance(85%))
					$pods=1
					if (have podSummonBoost) 
						$pods=10*pow(1.1,summonBoost)
					end
					yield $pods goldBeanPod
					yield $pods goldPodSummoned
					toast You summoned [$pods] golden bean [?($pods=1)|pod|pods]!
				else
					toast Failed to summon a golden bean pod.
				end
	    	end
		end
	*openPod
		name:Open golden bean pod
		desc:Open a golden bean pod with <b>[(5*pow(0.985,brittleShells))]</b> mana.
		icon:hat[0,0] https://cdn.rawgit.com/morkysherk/f8d8e087f0ba14052a1f2ba4920b5d0b/raw/3b51ba4c58bbb4eeeb58b89fb9fd2f9c97bde0d2/opened.svg
		no buy
		on click:
			if (mana>=(5*pow(0.985,brittleShells)) and goldBeanPods>=1)
				yield -(5*pow(0.985,brittleShells)) mana
				yield -1 goldBeanPod
				yield random(3,5) goldBeans
				toast Opened a golden bean pod!
	    	else if (goldBeanPods>=1)
				toast Not enough mana!
			else
				toast Not enough gold bean pods!
			end
		end
		tag:spell	
	*open10Pods
		name:Open 10 golden bean pods
		desc:Open 10 golden bean pods with <b>[(floor(45*pow(0.985,brittleShells)))]</b> mana.
		icon:hat[0,0] https://cdn.rawgit.com/morkysherk/1f3ef30050de604be0aa4d9ca6b09a96/raw/1fcd43fd14dcdf483a5650cc68b197de42ccfc38/open10.svg
		no buy
		on click:
			if (mana>=(floor(45*pow(0.985,brittleShells))) and goldBeanPods>=10)
				yield -(floor(45*pow(0.985,brittleShells))) mana
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield -1 goldBeanPod
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				yield random(3,5) goldBeans
				toast Opened 10 golden bean pods!
	    	else if (goldBeanPods>=10)
				toast Not enough mana!
			else
				toast Not enough golden bean pods!
			end
		end
		tag:spell
	*open100Pods
		name:Open 100 golden bean pods
		desc:Open 100 golden bean pods with <b>[(floor(405*pow(0.985,brittleShells)))]</b> mana.
		icon:hat[0,0] https://cdn.rawgit.com/morkysherk/ede7013df43ebee22d71bd8e36355b35/raw/3c77d28b365ba6d5772dd19a9ca57316982d5028/open100.svg
		no buy
		on open:
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
		end
		on click:
			if (mana>=(floor(405*pow(0.985,brittleShells))) and goldBeanPods>=100)
				yield -(floor(405*pow(0.985,brittleShells))) mana
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				do open with open100Pods
				toast Opened 100 golden bean pods!
	    	else if (goldBeanPods>=100)
				toast Not enough mana!
			else
				toast Not enough golden bean pods!
			end
		end
		tag:spell
	*open1000Pods
		name:Open 1,000 golden bean pods
		desc:Open 1,000 golden bean pods with <b>[(floor(3847*pow(0.985,brittleShells)))]</b> mana.<.>turning on full numbers is recommended when viewing the cost
		icon:hat[0,0] https://cdn.rawgit.com/morkysherk/cccba97b91da3a3ad27aa66457cd4a51/raw/3abf2752d43291b49d69baf91e94d5eac182024d/open1000.svg
		no buy
		on open:
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield -1 goldBeanPod
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
			yield random(3,5) goldBeans
		end
		on click:
			if (mana>=(floor(3847*pow(0.985,brittleShells))) and goldBeanPods>=100)
				yield -(floor(3847*pow(0.985,brittleShells))) mana
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				do open with open1000Pods
				toast Opened 1,000 golden bean pods!
	    	else if (goldBeanPods>=1000)
				toast Not enough mana!
			else
				toast Not enough golden bean pods!
			end
		end
		tag:spell

	*TEMPLATE
		class:smallThing thing
		on click:
			if (clickAnimation=1)
				anim icon wobble2
				anim wobble2
			end
			if (clickAnimation=2)
				anim icon bounceOnce
				anim bounceOnce
			end
			if (clickAnimation=3)
				anim icon plop
				anim plop
			end
			if (clickAnimation=4)
				anim icon wiggling2
				anim wiggling
			end
			if (clickAnimation=5)
				anim icon wobbleSlow
				anim wobbleSlow
			end
		end
		on earn:hide this
		tag:upgrade
		on earn:yield 1 ownedUpgradetxt
		on load:
			if (upgrCheck=0)
				yield 1 ownedUpgradetxt
			end
		end
		no text

	//RECIPES

	*cupRecipe
		name:Peanut butter cup recipe
		desc:Discover the ancient secrets of cupping peanut butter.<//><.>Unlocks peanut butter cup producers.
		cost:100 chocolate
		cost:100 peanutButter
		req:50 cEarnedThisUniverse
		req:50 pEarnedThisUniverse
		req:1 chocolateWorker
		req:1 peanutButterer
		icon:https://cdn.rawgit.com/morkysherk/0cdaa3a1509eb96be2bf37b4de20a0cd/raw/831ea35eca9b0eb008c038d929f7b3a112da4f2f/scroll.svg

	//GOLD BEAN UPGRADES

	*fourcloverLeaf
		name:Four clover leaf
		desc:Four leaf clovers may be rare, but has anyone ever seen one of these?<//><.>Golden peanut butter cups will appear <b>10%</b> more often.<.>Golden peanut butter cups will require <b>10</b> less mana to summon.
		passive:multiply frequency of luckyCup by 0.9
		cost:100 goldBeans
		req:7 lclicks
		icon:https://imgur.com/XGcyejq.png
		tags:upgrade beanUpgrade
	*luckyBoost
		name:Tiny lucky boost
		desc:Use the power of a small bit of luck to your benefit.<//><.>Boosts all production by <b>1%</b>.
		cost:100 goldBeans
		req:7 lclicks
		passive:multiply yield of tag:building by 1.03
		on earn:yield (multiplier*0.01) multiplier
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
		tags:upgrade beanUpgrade
	*podSummonBoost
		name:Golden bean pod summoning boost
		desc:<.>Get <b>10</b> golden bean pods per "Spawn golden bean pod" cast instead of 1.<.>Unlocks a spell boost to increase the yield of each cast.
		cost:1500 goldBeans
		req:7 lclicks
		icon:numbers[0,0] https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
		tags:upgrade beanUpgrade
	*blackcatHorseshoe
		name:Black cat's horseshoe
		desc:Just don't let it cross your path.<//><.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15</b> less mana to summon.<.>Golden peanut butter cups will have slightly boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:1000 goldBeans
		cost:1 crystalBean
		req:10 lclicks
	icon:https://cdn.rawgit.com/morkysherk/9c6691e4d32e6a90df9b98214453bc89/raw/a947c17d45a345c4c2e458f61fd454a21e074a0a/blackcatHorseshoe.svg
		tags:upgrade beanUpgrade
	*smallLuckyBoost
		name:Relatively small lucky boost
		desc:Use the power of a little more luck to your benefit.<//><.>Boosts all production by <b>1.5%</b>.
		cost:1000 goldBeans
		cost:1 crystalBean
		req:10 lclicks
		passive:multiply yield of tag:building by 1.015
		on earn:yield (multiplier*0.015) multiplier
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
		tags:upgrade beanUpgrade
	*halfRainbow
		name:Half Rainbow
		desc:Halfway across the sky!<//><.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15<b> less mana to summon.<.>Golden peanut butter cups will have moderately boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:5000 goldBeans
		cost:3 crystalBeans
		req:17 lclicks
	icon:https://cdn.rawgit.com/morkysherk/39a168e26cc819f1ad359d3dc22ea8c1/raw/848323dde50f89f9199012ed70644b4b9df66bd6/halfRainbow.svg
		tags:upgrade beanUpgrade
	*fairlyLuckyBoost
		name:Fairly lucky boost
		desc:Use the power of a fair bit of luck to your benefit.<//><.>Boosts all production by <b>2%</b>.
		cost:5000 goldBeans
		cost:3 crystalBeans
		req:17 lclicks
		passive:multiply yield of tag:building by 1.02
		on earn:yield (multiplier*0.02) multiplier
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
		tags:upgrade beanUpgrade
	*closedUmbrella
		name:Closed umbrella
		desc:Keep it inside.<//><.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15<b> less mana to summon.<.>Golden peanut butter cups will have boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:20000 goldBeans
		cost:10 crystalBeans
		req:37 lclicks
	icon:https://cdn.rawgit.com/morkysherk/61ef6c72d66f667cc67f8046a86dd747/raw/5ec7158eba2de361820a4fa2a3ebfc26dbb90049/closedUmbrella.svg
		tags:upgrade beanUpgrade
	*sizableLuckyBoost
		name:Sizable lucky boost
		desc:Use the power of a decent amount of luck to your benefit.<//><.>Boosts all production by <b>2.5%</b>.
		cost:20000 goldBeans
		cost:10 crystalBeans
		req:37 lclicks
		passive:multiply yield of tag:building by 1.02
		on earn:yield (multiplier*0.02) multiplier
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
		passive:multiply yield of tag:building by 1.025
		on earn:yield (multiplier*0.025) multiplier
		tags:upgrade beanUpgrade
	*d7
		name:7 sided die
		desc:Just the right amount of rigged.<.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15</b> less mana to summon.<.>Golden peanut butter cups will have more boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:100000 goldBeans
		cost:50 crystalBeans
		req:57 lclicks
		icon:https://cdn.rawgit.com/morkysherk/0cba993d0942bc96e859120ddb03bc6e/raw/6d495d3d593523d9d8cbad59113f0c3277f2a131/d7.svg
		tags:upgrade beanUpgrade
	
	//RESOURCE CLICKING

	*peanutcupClicking
		name:Peanut Butter Cup Clicking
		desc:Clicking either button 3 times will produce a peanut butter cup.
		cost:1000 peanutCups
		req:1 peanutCup:ps
		req:notaButton
		icon:https://imgur.com/Pu0f5pK.png
	*combinedClicking
		name:Combined Clicking
		desc:Clicking the chocolate twice will produce a jar of peanut butter, and vice versa.
		cost:10000 chocolate
		cost:10000 peanutButter
		req:1000 chocoButton clicks
		req:1000 pButton clicks
		icon:https://imgur.com/kTtlgRR.png

	//BETTER BUTTON UPGRADES

	*betterButton
		name:Better Button
		desc:Now with 100% more!<//><.>The peanut butter button will produce <b>twice</b> as much peanut butter, and the chocolate button will yield <b>twice</b> as much chocolate.<.>Multiplies yield of autoclickers by <b>2</b>.
		cost:100 chocolate
		cost:100 peanutButter
		passive:multiply chocolate yield of chocoButton by 2
		passive:multiply peanutButter yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2
		passive:multiply peanutButter yield of clicker by 2
		req:1 cEarnedThisUniverse
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*betterButton2
		name:Better Button II
		desc:Just compare it to the leading brand!<//><.>The peanut butter button will produce <b>twice</b> as much peanut butter, and the chocolate button will yield <b>twice</b> as much chocolate.<.>Multiplies yield of autoclickers by <b>2</b>.
		cost:1000 chocolate
		cost:1000 peanutButter
		passive:multiply chocolate yield of chocoButton by 2
		passive:multiply peanutButter yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2
		passive:multiply peanutButter yield of clicker by 2
		req:betterButton
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*betterButton3
		name:Better Button III
		desc:We'll double the offer!<//><.>Multiplies all yield of buttons by <b>2</b>.<.>Multiplies yield of clickers by <b>2.25</b>.
		cost:5000 chocolate
		cost:5000 peanutButter
		cost:1000 peanutCups
		req:betterButton2
		passive:multiply yield of chocoButton by 2
		passive:multiply yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2.25
		passive:multiply peanutButter yield of clicker by 2.25
		passive:multiply goldBeanPod yield of clicker by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*betterButton4
		name:Better Button IV
		desc:But wait, there's more!<//><.>Multiplies yield of buttons by <b>2</b>.<.>Multiplies yield of clickers by <b>2.5</b>.
		cost:50000 chocolate
		cost:50000 peanutButter
		cost:25000 peanutCups
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply yield of chocoButton by 2
		passive:multiply yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2.5
		passive:multiply peanutButter yield of clicker by 2.5
		passive:multiply goldBeanPod yield of clicker by 2
		req:betterButton3
	*betterButton5
		name:Better Button V
		desc:Call now and you'll receive a mini button too!<//><.>Clicking either button will produce <b>7.5%</b> more chocolate, peanut butter, and peanut butter cups per chocolate worker and peanut butterer.<.>Multiplies yield of autoclickers by <b>2.75</b>.
		cost:500000 chocolate
		cost:500000 peanutButter
		cost:300000 peanutCups
		icon:numbers[5,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply chocolate yield of chocoButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply chocolate yield of pButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutButter yield of chocoButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutButter yield of pButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutCup yield of chocoButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutCup yield of pButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply chocolate yield of clicker by 2.75
		passive:multiply peanutButter yield of clicker by 2.75
		req:betterButton4
	*betterButton6
		name:Better Button VI
		desc:Are you tired of this? <i>clicks button and gets nothing</i><//><.>Clicking either button will produce <b>15%</b> more chocolate, peanut butter, and peanut butter cups per chocolate farm and peas and nuts converter.<.>Combined and peanut butter cup clicking are twice as effective.<.>Multiplies yield of autoclickers by <b>3</b>.
		cost:5000000 chocolate
		cost:5000000 peanutButter
		cost:3000000 peanutCups
		icon:numbers[6,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply chocolate yield of chocoButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply chocolate yield of pButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutButter yield of chocoButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutButter yield of pButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutCup yield of chocoButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutCup yield of pButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply chocolate yield of pButton by 2
		passive:multiply peanutButter yield of chocoButton by 2
		passive:multiply peanutCup yield of pButton by 2
		passive:multiply peanutCup yield of chocoButton by 2
		passive:multiply chocolate yield of clicker by 3
		passive:multiply peanutButter yield of clicker by 3
		req:betterButton5
	*betterButton7
		name:Better Button VII
		desc:Woops, looks like I'm all out of ideas.<.>Clicking either button will produce <b>22.5%</b> more chocolate, peanut butter, and peanut butter cups per refinery and factory.<.>Multiplies yield of autoclickers by <b>3.25</b>.
		cost:500000000 chocolate
		cost:500000000 peanutButter
		cost:300000000 peanutCups
		icon:numbers[7,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply chocolate yield of chocoButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply chocolate yield of pButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutButter yield of chocoButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutButter yield of pButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutCup yield of chocoButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutCup yield of pButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply chocolate yield of clicker by 3.25
		passive:multiply peanutButter yield of clicker by 3.25
		req:betterButton6

	//CUP TYPES

	*darkCups
		name:Dark chocolate peanut butter cups
		desc:These more bitter cups will balance out the sweet peanut butter, and add <b>2%</b> to your production multiplier.
		cost:10000 peanutCups
		passive:multiply yield of tag:building by 1.02
		on earn:yield (multiplier*0.02) multiplier
		req:1000 earnedThisUniverse
	   icon:https://cdn.rawgit.com/morkysherk/cc542868ef20cfc9b7423346a66a808b/raw/5e6f2c64dcd5f775fe7cc77248c856a4cdf39c11/dankCup.svg
	*whiteCups
		name:White chocolate peanut butter cups
		desc:These cups will add another <b>3%</b> to your production multiplier.
		passive:multiply yield of tag:building by 1.03
		on earn:yield (multiplier*0.03) multiplier
		cost:100000 peanutCups
		req:10000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/d62cf2cc2aa0ff9bb14820ac32ecf6b4/raw/629d7d32e5c0224ffc69f1eff0a76bba492e01c2/white.svg
	*miniCups
		name:Mini peanut butter cups
		desc:These tiny peanut butter cups will go a long way by adding <b>5%</b> to your production multiplier.
		passive:multiply yield of tag:building by 1.05
		on earn:yield (multiplier*0.05) multiplier
		cost:10000000 peanutCups
		req:1000000 earnedThisUniverse
		icon:https://cdn.rawgit.com/morkysherk/c535202fb639a334a9e92a9f742823f1/raw/e11ecf49f7fd4f7407e26eea00445bd645e308ed/mini.svg
	*cookieCups
		name:Cookies and cream peanut butter cups
		desc:Combine the addicting flavor or cookies and cream with the divine taste of peanut butter cups to earn another <b>+5%</b> to your production multiplier.
		passive:multiply yield of tag:building by 1.05
		on earn:yield (multiplier*0.05) multiplier
		req:100000000 earnedThisUniverse
		cost:1000000000 peanutCups
		icon:https://cdn.rawgit.com/morkysherk/448400d1ea3175f67a88555781cd44dc/raw/bee0e63623a77f7dbb8fcdabd7e5c2ecb0baf53c/ccCup.svg

	//ACHIEVEMENT BONUSES
		
	*whiteRibbon
		name:White Ribbon
		desc:3rd...<.>Increases your multiplier by <b>0.5%</b> per achievement earned.
		cost:1000000 peanutCups
		cost:1000000 chocolate
		cost:1000000 peanutButter
	   icon:https://cdn.rawgit.com/morkysherk/c261f5c738d6b695d9af0bfd0f4dfd47/raw/7f0e2dc43469121e2c6bda2ac259a221e77ea5cc/ribbon3.svg
		passive:multiply yield of tag:building by (1+(0.005*(achievPoints)))
		req:15 achievPoints
	*redRibbon
		name:Red Ribbon
		desc:2nd...<.>Increases your multiplier by <b>0.75%</b> per achievement earned.
		cost:10000000000 peanutCups
		cost:10000000000 chocolate
		cost:10000000000 peanutButter
	   icon:https://cdn.rawgit.com/morkysherk/3dbf8f73ce882152bbdf5078ffcf4262/raw/2e3a0f05291acecc7e3dacce36b9da723b0c4642/ribbon2.svg
		passive:multiply yield of tag:building by (1+(0.0075*(achievPoints)))
		req:35 achievPoints
	*blueRibbon
		name:Blue Ribbon
		desc:1st place!<.>Increases your multiplier by <b>1%</b> per achievement earned.
		cost:100000000000000 peanutCups
		cost:100000000000000 chocolate
		cost:100000000000000 peanutButter
	   icon:https://cdn.rawgit.com/morkysherk/8d46797cc8e4ddecab5bd6f5e4326ed0/raw/4d6e564c983317170c40b6915f17ecee8c8225f6/ribbon1.svg
		passive:multiply yield of tag:building by (1+(0.01*(achievPoints)))
		req:75 achievPoints

	//OTHER

	*gainfulPain
		name:Gainful pain
		desc:oof<.>Boosts peanut butter cup production by <b>50%</b> when chocolate or peanut butter production is negative.
		req:loss
		on tick:
			if (peanutButter:ps<0 or chocolate:ps<0)
				yield (peanutCups:ps/2) peanutCups
			end
		end
		icon:https://cdn.rawgit.com/morkysherk/22804416129794044b726fc47b0ab198/raw/c4683db1a1002a50fb139d41c770cb02405c21cd/+-.svg
			

	//WORKER UPGRADES

	*training
		name:Training
		desc:Trained workers just might be more efficient.<//><.>Chocolate workers, peanut butterers, and peanut butter cuppers are <b>50%</b> faster.
		cost:1000 chocolate
		cost:1000 peanutButter
		cost:500 peanutCups
		req:10 chocolateWorkers:max
		req:10 peanutButterers:max
		req:1 peanutCupper:max
		passive:multiply yield of chocolateWorkers by 1.5
		passive:multiply yield of peanutButterers by 1.5
		passive:multiply yield of peanutCuppers by 1.5
	    icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/3e0ec7b2a12853b346b0a51c1758592d/raw/017fbaa567ab0c82a2ac5dea0ab4e1ab60bf38b8/gradCap.svg
	*collegeEducation
		name:Working smarter
		desc:Not harder.<//><.>Chocolate workers, peanut butterers, and peanut butter cuppers are <b>50%</b> faster.
		cost:10000 chocolate
		cost:10000 peanutButter
		cost:100 peanutCups
		req:25 chocolateWorkers:max
		req:25 peanutButterers:max
		req:10 peanutCuppers:max
		passive:multiply yield of chocolateWorkers by 1.5
		passive:multiply yield of peanutButterers by 1.5
		passive:multiply yield of peanutCuppers by 1.5
	    icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/3e0ec7b2a12853b346b0a51c1758592d/raw/017fbaa567ab0c82a2ac5dea0ab4e1ab60bf38b8/gradCap.svg
	*collegeEducationA
		name:College education
		desc:I have a PhD in making peanut butter cups.<//><.>Chocolate workers, peanut butterers, and peanut butter cuppers are <b>50%</b> faster.
		cost:100000 chocolate
		cost:100000 peanutButter
		cost:1000 peanutCups
		req:50 chocolateWorkers:max
		req:50 peanutButterers:max
		req:25 peanutCuppers:max
		passive:multiply yield of chocolateWorkers by 1.5
		passive:multiply yield of peanutButterers by 1.5
		passive:multiply yield of peanutCuppers by 1.5
	    icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/3e0ec7b2a12853b346b0a51c1758592d/raw/017fbaa567ab0c82a2ac5dea0ab4e1ab60bf38b8/gradCap.svg

	//CHOCOLATE WORKER UPGRADES	

	*fasterRoasting
		name:Faster roasting
		desc:Chocolate workers roast cocoa beans faster.<//><.>Multiplies yield of chocolate workers by <b>2</b>.
		cost:500 chocolate
		req:1 chocolateWorker:max
		passive:multiply yield of chocolateWorker by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*literalchocoWorkers
		name:Literal chocolate workers
		desc:Chocolate workers are now made of chocolate, which makes them faster. Don't ask.<//><.>Multiplies yield of chocolate workers by <b>2</b>.
		cost:5000 chocolate
		req:10 chocolateWorker:max
		passive:multiply yield of chocolateWorker by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*mitosis
		name:Higher melting point
		desc:You've run into some problems with melting workers.<//><.>Multiplies yield of chocolate workers by <b>2</b>.
		cost:50000 chocolate
		passive:multiply yield of chocolateWorker by 2
		req:25 chocolateWorkers:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*mitosis1
		name:Mitosis
		desc:why do i have to give birth why can't i just do my toast is<//><.>Multiplies yield of chocolate workers by <b>4</b>.<.><i>End of tier 1</i>
		cost:500000 chocolate
		passive:multiply yield of chocolateWorker by 4
		req:50 chocolateWorkers:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*reinforcedWorkers
		name:Reinforced chocolate workers
		desc:Industrial strength.<.>Multiplies yield of chocolate workers by <b>3</b>.<.>
		cost:5000000 chocolate
		passive:multiply yield of chocolateWorker by 3
		req:75 chocolateWorkers:max
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*whiteChocoWorkers
		name:White chocolate workers
		desc:The sweetest little guys you've ever met. Also pretty creamy.<.>Multiplies yield of chocolate workers by <b>3</b>.<q>white supremacist idle game makes the white workers better!! wee woo wee woo sound the alarm!</q>
		cost:50000000 chocolate
		passive:multiply yield of chocolateWorker by 3
		req:100 chocolateWorkers:max
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
/*
	*bronzeChocoBar
		name:Bronze chocolate bar
		cost:1500 goldBeans
		desc:a feature
	icon:https://cdn.rawgit.com/morkysherk/bc9dc27462ac807b80357f97ee30c6c2/raw/3bbc191e569ad8ca197bea308d80c1042effbb8e/chocobarbronze.svg
	*silverChocoBar
		name:Silver chocolate bar
		cost:4500 goldBeans
		desc:a feature
	icon:https://cdn.rawgit.com/morkysherk/652c6258f895bc341b2877edcf47977b/raw/2410a9706e8b7a5c627d1b6527fa919661d929b6/chocsilver.svg
	*goldChocoBar
		name:Golden chocolate bar
		cost:22500 goldBeans
		desc:a feature
	  icon:https://cdn.rawgit.com/morkysherk/2f3779e36d4e51dcf119f736965c23b0/raw/d0c182746840fa50103223f9ae0282d9a4fcddfa/chocgold.svg
	*crystalChocoBar
		name:Crystal chocolate bar
		cost:157500 goldBeans
		desc:a feature
	icon:https://cdn.rawgit.com/morkysherk/7836391057ed4ceea8946de1d042bb58/raw/f22300d877fdff866df64b911bf6a125e73edefb/choccrystal.svg
*/

	//FARM UPGRADES

	*refinedRefineries
		name:Fertilizer
		desc:Enhance your trees' growth rates.<//><.>Multiplies yield of farms by <b>2</b>.
		cost:7500 chocolate
		passive:multiply yield of refinery by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:1 refinery:max
	*fasterGrinders
		name:Healthier seeds
		desc:Make them healthier before they even start growing.<//><.>Multiplies yield of farms by <b>2</b>.
		cost:75000 chocolate
		req:10 refineries:max
		passive:multiply yield of refinery by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*extraMixable
		name:Flavored water
		desc:Drinking regular water every day must get boring.<//><.>Multiplies yield of farms by <b>2</b>.
		cost:750000 chocolate
		passive:multiply yield of refinery by 2
		req:25 refineries:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocosynthesis
		name:Chocosynthesis
		desc:Convert sunlight into chocolate instead of sugar.<.>Multiplies yield of farms by <b>4</b>.<.><i>End of tier 1</i>
		cost:7500000 chocolate
		passive:multiply yield of refinery by 4
		req:50 refineries:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocoSoil
		name:Chocolate soil
		desc:Makes walking around the farms a relatively unpleasant experience, but helps your trees grow.<.>Multiplies yield of farms by <b>3</b>.
		cost:75000000 chocolate
		passive:multiply yield of refinery by 3
		req:75 refineries:max
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocoWeeds
		name:Chocolate weeds
		desc:Make those pesky plants into efficient chocolate producers.<.>Multiplies yield of farms by <b>3</b>.
		cost:750000000 chocolate
		passive:multiply yield of refinery by 3
		req:100 refineries:max
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
/*
	*bronzePod
		name:Bronze chocolate pod
		desc:a feature
		icon:https://goo.gl/WzWiuc
	*silverPod
		name:Silver chocolate pod
		desc:a feature
		icon:https://goo.gl/Po4jnP
	*goldPod
		name:Golden chocolate pod
		desc:a feature
		icon:https://goo.gl/TRWfWg
	*crystalPod
		name:Crystal chocolate pod
		desc:a feature
		icon:https://goo.gl/DtKnZk
*/

	//REFINERY UPGRADES

	*refinedRefineriesA
		name:Refined refineries
		desc:Refined refineries refine refined-er chocolate.<//><.>Multiplies yield of refineries by <b>2</b>.
		cost:112500 chocolate
		passive:multiply yield of chocoFarm by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:1 chocoFarm:max
	*fasterGrindersA
		name:Faster grinders
		desc:griiiiind<//><.>Multiplies yield of refineries by <b>2</b>.
		cost:1125000 chocolate
		passive:multiply yield of chocoFarm by 2
		req:10 chocoFarms:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
	*extraMixableA
		name:Extra mixable cocoa
		desc:The liquid cocoa will mix more quickly with other ingredients.<//><.>Multiplies yield of refineries by <b>2</b>.
		cost:11250000 chocolate
		passive:multiply yield of chocoFarm by 2
		req:25 chocoFarms:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
	*decombobulators
		name:Discombobulators
		desc:An important part of chocolate discombobulation.<//><.>Multiplies yield of refineries by <b>4</b>.<.><i>End of tier 1</i>
		cost:112500000 chocolate
		passive:multiply yield of chocoFarm by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:50 chocoFarms:max
/*
	*bronzeGrinder
		name:Bronze cocoa grinder
		cost:33750 goldBean
		desc:a feature
  icon:https://cdn.rawgit.com/morkysherk/f4bb8783a31ee0f26b229d614da86e12/raw/8da189e51faf5d5a09960f85452ea49e5d320905/refineBronze.svg
	*silverGrinder
		name:Silver cocoa grinder
		cost:101250 goldBean
		desc:a feature
    icon:https://cdn.rawgit.com/morkysherk/facff1cb86ae9dc631304589d09bccd9/raw/c823491e173e9ed1707263ec60faa5449f84ebc2/refineSilv.svg
	*goldenGrinder
		name:Golden cocoa grinder
		cost:506250 goldBean
		desc:a feature
    icon:https://cdn.rawgit.com/morkysherk/4906f4a614109f5551105c11eb41ddc8/raw/a50fd1be5301262a7c2491fa6943f92a23d172ac/refineGold.svg
	*crystalGrinder
		name:Crystal cocoa grinder
		cost:3543750 goldBean
		desc:a feature
   icon:https://cdn.rawgit.com/morkysherk/ddcc9c051ae0c268d6797e0a37bfd2d9/raw/43b09fc67b36888ea0bcea1e978e0a7e327f438d/refineCrys.svg
*/

	//BUTTERER UPGRADES

	*fastProcessors
		name:Faster food processors
		desc:Peanut butterers use faster food processors.<//><.>Multiplies yield of peanut butterers by <b>2</b>.
		cost:500 peanutButter
		passive:multiply yield of peanutButterer by 2
		req:1 peanutButterer:max
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*softerPeanuts
		name:Softer peanuts
		desc:Peanuts are softer, and can be processed faster.<//><.>Multiplies yield of peanut butterers by <b>2</b>.
		cost:5000 peanutButter
		passive:multiply yield of peanutButterer by 2
		req:10 peanutButterers:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*biggerProcessors
		name:Bigger processors
		desc:More room to shove your peanuts into.<//><.>Multiplies yield of peanut butterers by <b>2</b>.
		cost:50000 peanutButter
		passive:multiply yield of peanutButterer by 2
		req:25 peanutButterers:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*cProcessors
		name:Computer processors
		desc:Are you sure these'll work?<//><.>Multiplies yield of peanut butterers by <b>4</b><.><i>End of tier 1</i>
		cost:500000 peanutButter
		passive:multiply yield of peanutButterer by 4
		req:50 peanutButterers:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
/*
	*bronzePB
		name:Bronze peanut butter jar
		cost:1 goldBean
		desc:a feature
	icon:https://cdn.rawgit.com/morkysherk/a0e57a81d36393239966e36d64e0efc0/raw/937e5fc79bbfab264451290e53ea2dc94bd16337/peabBronze.svg
	*silverPB
		name:Silver peanut butter jar
		cost:1 goldBean
		desc:a feature
	icon:https://cdn.rawgit.com/morkysherk/72e2431054895f324d1885b09f0f7217/raw/89adcdd7556ef41476cb97cbfc12ad2aa4daee2a/peabSilver.svg
	*goldPB
		name:Golden peanut butter jar
		cost:1 goldBean
		desc:a feature
	  icon:https://cdn.rawgit.com/morkysherk/b16462a34af30db59724b84a461f19c8/raw/b7f8f57bdf5211b93e0b9e54472e07b6c3e1002d/peabGold.svg
	*crystalPB
		name:Crystal peanut butter jar
		cost:1 goldBean
		desc:a feature
   icon:https://cdn.rawgit.com/morkysherk/5f3b3e3fbf6cdd7f2c9b73b2e8f2dd6b/raw/60452f1fa9fa44c93bad8a20f0a4c75d8cb60c28/peabCrystal.svg
*/

	//CONVERTER UPGRADES
	
	*movingAssembly
		name:Better ratio
		desc:Needs less pea and more nut!<//><.>Multiplies yield of peas and nuts converters by <b>2</b>.
		cost:7500 peanutButter
		passive:multiply yield of pbFactory by 2
		req:1 pbFactory:max
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*factored
		name:Wider nut variety
		desc:More kinds of nuts to convert.<//><.>Multiplies yield of peas and nuts converters by <b>2</b>.
		cost:75000 peanutButter
		passive:multiply yield of pbFactory by 2
		req:10 pbFactories:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*factorial
		name:Green bean converter
		desc:Kinda similar to peas? I guess?<.>Multiplies yield of peas and nuts converters by <b>2</b>.
		cost:750000 peanutButter
		req:25 pbFactories:max
		passive:multiply yield of pbFactory by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*secretIngredient
		name:Secret ingredient
		desc:This Woman Found The Secret Ingredient To Quick Conversion! Peanut Butter Companies <b>HATE</b> Her! Click <b>HERE</b> To Find Out Her One Simple Trick!<//><.>Multiplies yield of peas and nuts converters by <b>4</b>.<.><i>End of tier 1</i>
		cost:7500000 peanutButter
		req:50 pbFactories:max
		passive:multiply yield of pbFactory by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
/*
	*bronzePeaNut
		name:Bronze pea and nut
		cost:1 goldBean
		desc:a feature
	icon:https://cdn.rawgit.com/morkysherk/ca6a3b1468179467b9d400094c71da60/raw/d0ae31a82d265cfe22eb6f6786f2548a88775884/convBronze.svg
*/
	
	//FACTORY UPGRADES
	
	*movingAssemblyA
		name:Moving assembly line
		desc:Aren't these pretty much the default these days?<//><.>Multiplies yield of peanut butter factories by <b>2</b>.
		cost:112500 peanutButter
		passive:multiply yield of factories by 2
		req:1 factories:max
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*factoredA
		name:Factored factories
		desc:In simplest form.<//><.>Multiplies yield of peanut butter factories by <b>2</b>.
		cost:1125000 peanutButter
		passive:multiply yield of factories by 2
		req:10 factories:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*factorialA
		name:Factorial factories
		desc:Surprisingly, 200-40*2 is only 5!<//><.>Multiplies yield of peanut butter factories by <b>2</b>.
		cost:11250000 peanutButter
		req:25 factories:max
		passive:multiply yield of factories by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*scaleFactor
		name:Scale factor
		desc:Dilated by a scale factor of 2.<//><.>Multiplies yield of peanut butter factories by <b>4</b>.<.><i>End of tier 1</i>
		cost:112500000 peanutButter
		req:50 factories:max
		passive:multiply yield of factories by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg

	//REPLICATOR UPGRADES
	
	*triplers
		name:Triplers
		desc:Get an extra bar of chocolate and jar of peanut butter every time.<//><.>Multiplies yield of replicators by <b>2</b>.
		cost:1687500 chocolate
		cost:1687500 peanutButter
		req:1 replicator:max
		icon:https://cdn.rawgit.com/morkysherk/c399adb84f6c2b88465731f8ec1353e9/raw/05801ea4697148eb702ca01ff573a6bec4381af5/x3.svg
		passive:multiply yield of replicators by 2
	*quintuplers
		name:Quintuplers
		desc:Get 3 extra bars of chocolate and jars of peanut butter every time.<//><.>Multiplies yield of replicators by <b>2</b>.
		cost:16875000 chocolate
		cost:16875000 peanutButter
		req:10 replicators:max
		icon:https://cdn.rawgit.com/morkysherk/f0ee659a64b86417081498339daa784e/raw/d61355dcc84be9bbbe53deb20acd657326c28e0a/x5.svg
		passive:multiply yield of replicators by 2
	*nonuplers
		name:Nonuplers
		desc:Get 7 extra bars of chocolate and jars of peanut butter every time.<//><.>Multiplies yield of replicators by <b>2</b>.
		cost:168750000 chocolate
		cost:168750000 peanutButter
		req:25 replicators:max
		icon:https://cdn.rawgit.com/morkysherk/a9ce3fbbccb4f2cd425c1866a099718a/raw/0b8c26732d0a1f764af3b43bdd886d31472b48e0/x9.svg
		passive:multiply yield of replicators by 2
	*tretrigintuplers
		name:Tretrigintuplers
		desc:I couldn't quite fit the X in, sorry.<//><.>Multiplies yield of replicators by <b>4</b>.<.><i>End of tier 1</i>
		cost:1687500000 chocolate
		cost:1687500000 peanutButter
		req:50 replicators:max
		icon:https://cdn.rawgit.com/morkysherk/61d92ff0ff3b0faac72c45ae246d5b48/raw/cf73df6ee2f1d2c99b70d5150f20d9f7926a8009/x33.svg
		passive:multiply yield of replicators by 4

	//CORE EXTRACTOR UPGRADES

	*deeperExtraction
		name:Deeper extraction
		desc:Go deeper into the planet's delicious, gooey core.<.>Multiplies yield of core extractors by <b>2</b>.
		cost:27000000 chocolate
		cost:27000000 peanutButter
		req:1 coreExtractor:max
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		passive:multiply yield of coreExtractor by 2
	*coolers
		name:Coolers
		desc:Make your scorching hot peanut butter and chocolate nice and cool. As a side effect, you may catch them using the latest trendy lingo.<.>Multiplies yield of core extractors by <b>2</b>.
		cost:270000000 chocolate
		cost:270000000 peanutButter
		req:10 coreExtractors:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		passive:multiply yield of coreExtractor by 2
	*fasterTransportation
		name:Faster transportation
		desc:Sure takes a while for things to get from the core to the surface.<.>Multiplies yield of core extractors by <b>2</b>.
		cost:2700000000 chocolate
		cost:2700000000 peanutButter
		req:25 coreExtractors:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		passive:multiply yield of coreExtractor by 2
	*otherPlanets
		name:Other planets
		desc:Extracting from other planets' cores has a much higher output! It's also less damaging to Earth but that's not what matters.<.>Multiplies yield of core extractors by <b>4</b>.<.><i>End of tier 1</i>
		cost:27000000000 chocolate
		cost:27000000000 peanutButter
		req:50 coreExtractors:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/2ce082b468d4fb8335ca2b2585e9612c/raw/b667b66cc0b191e872c9f4ce1792316a03942b51/otherPlanet.svg
		passive:multiply yield of coreExtractor by 4

	//DOWNLOADER UPGRADES

	*quantumPBC
		name:Quantum peanut butter and chocolate
		desc:It's quantum compatible!<.>Multiplies yield of quantum downloaders by <b>2</b>.
		cost:800000000 chocolate
		cost:800000000 peanutButter
		req:1 qDownloader:max
		passive:multiply yield of qDownloaders by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*gbWifi
		name:Gigabit Wi-Fi
		desc:gotta download fast<.>Multiplies yield of quantum downloaders by <b>2</b>.
		cost:8000000000 chocolate
		cost:8000000000 peanutButter
		req:10 qDownloaders:max
		passive:multiply yield of qDownloaders by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*qMechanic
		name:A quantum mechanic
		desc:Fixes your quantum downloaders when they break.<.>Multiplies yield of quantum downloaders by <b>2</b>.
		cost:80000000000 chocolate
		cost:80000000000 peanutButter
		req:25 qDownloaders:max
		passive:multiply yield of qDownloaders by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*qInternet
		name:Quantum internet
		desc:At this point, why not just make everything quantum?<.>Multiplies yield of quantum downloaders by <b>4</b>.<.><i>End of tier 1</i>
		cost:800000000000 chocolate
		cost:800000000000 peanutButter
		req:50 qDownloaders:max
		passive:multiply yield of qDownloaders by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg

	//MIND READER UPGRADES

	*ads
		name:Advertisements
		desc:Spread the word!<.>Multiplies yield of mind readers by <b>2</b>.
		passive:multiply yield of mindReaders by 2
		req:1 mindReader:max
		cost:25600000000 chocolate
		cost:25600000000 peanutButter
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg
	*subliminal
		name:Subliminal messaging
		desc:<.>Multiplies yield of mind readers by <b>2</b>.
		passive:multiply yield of mindReaders by 2
		req:10 mindReaders:max
		cost:256000000000 chocolate
		cost:256000000000 peanutButter
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg
	*hallucinogens
		name:Hallucinogens
		desc:if I wasn't eating chocolate that whole time... what was I eating?<.>Multiplies yield of mind readers by <b>2</b>.
		passive:multiply yield of mindReaders by 2
		req:25 mindReaders:max
		cost:2560000000000 chocolate
		cost:2560000000000 peanutButter
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg
	*mindControl
		name:Mind control
		desc:Put on your tinfoil hats!<.>Multiplies yield of mind readers by <b>4</b>.
		passive:multiply yield of mindReaders by 4
		req:50 mindReaders:max
		cost:25600000000000 chocolate
		cost:25600000000000 peanutButter
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg

	//CUPPER UPGRADES
		
	*nimbleFingers
		name:Nimble fingers
		desc:Trim off the fat and get some muscle memory.<//><.>Multiplies yield of peanut butter cuppers by <b>2</b>.
		cost:1000 chocolate
		cost:1000 peanutButter
		cost:250 peanutCups
		req:1 peanutCupper:max
		passive:multiply yield of peanutCupper by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*cupManufacturers
		name:Cup manufacturers
		desc:These guys have a lot of experience making cups. That should translate well into making peanut butter cups, right?<//><.>Multiplies yield of peanut butter cuppers by <b>2</b>.
		cost:10000 chocolate
		cost:10000 peanutButter
		cost:2500 peanutCups
		req:10 peanutCuppers:max
		passive:multiply yield of peanutCupper by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*chefs
		name:Chefs
		desc:Cooks up some fresh peanut butter cups.<//><.>Multiplies yield of peanut butter cuppers by <b>2</b>.<q>Are the peanut butter cups fresh or frozen?</q>
		cost:100000 chocolate
		cost:100000 peanutButter
		cost:25000 peanutCups
		req:25 peanutCuppers:max
		passive:multiply yield of peanutCupper by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*mages
		desc:Casts spells on your peanut butter and chocolate to form peanut butter cups.<.>Multiplies yield of peanut butter cuppers by <b>4</b>.<.><i>End of tier 1</i>
		name:Mages
		cost:1000000 chocolate
		cost:1000000 peanutButter
		cost:250000 peanutCups
		req:50 peanutCuppers:max
		passive:multiply yield of peanutCupper by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
/*
	*awwwawdwdwd awda d ddddddOOOOOOOOOOO
		name:Seemeeks cube
		desc:If you don't get this, you probably don't have a solid enough grasp of theoretical physics.<.>Multiplies yield of peanut butter cuppers by <b>4</b>.<//><q>"CAN DO!"</q>
		icon:numbers[5,0] https://imgur.com/XyuOrLu.png
		req:51 peanutCuppers:max
		cost:1000000 chocolate
		cost:1000000 peanutButter
		cost:250000 peanutCups
		passive:multiply yield of peanutCupper by 3
*/

	//MACHINE UPGRADES
		
	*wc
		name:WC-50
		desc:Makes things go.<//><.>Multiplies yield of cup machines by <b>2</b>.
		cost:15000 peanutCups
		req:1 cupMachine:max
		passive:multiply yield of cupMachine by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*cheaperMetal
		name:Cheaper Metal
		desc:Refineries, factories, and machines are <b>5%</b> cheaper.
		cost:75000 peanutCups
		passive:multiply cost of cupMachine by 0.95
		passive:multiply cost of factory by 0.95
		passive:multiply cost of chocoFarm by 0.95
		req:5 cupMachines:max
		req:10 factories:max
		req:10 chocoFarms:max
		icon:https://cdn.rawgit.com/morkysherk/82a70ae5ca004b88d52db0a8d383bc16/raw/84927ce67cde4be2717272266a06565771220240/dolla.svg
	*lighterMachinery
		name:Lighter Machinery
		cost:150000 peanutCups
		desc:Try our new weight loss programs for machines!<.>Multiplies yield of cup machines by <b>2</b>.
		req:10 cupMachines:max
		passive:multiply yield of cupMachines by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*hqCogs
		name:High quality cogs
		cost:1500000 peanutCups
		desc:For smoother rotation.<.>Multiplies yield of cup machines by <b>2</b>.
		passive:multiply yield of cupMachines by 2
		req:25 cupMachines:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*microMachines
		name:Micro-machines
		cost:15000000 peanutCups
		desc:These can move anything anywhere, with ease. If you can think it, they can do it. The only limit is your imagination.<.>Multiplies yield of cup machines by <b>4</b>.<.><i>End of tier 1</i>
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
		req:50 cupMachines:max
		passive:multiply yield of cupMachines by 2

	//PRINTER UPGRADES

	*fasterPrinting
		name:Faster printers
		desc:The printhead can move faster.<//><.>Multiplies yield of 3D printers by <b>2</b>.
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:175000 peanutCups
		passive:multiply yield of printers by 2
		req:1 printer:max
	*optimizedModels
		name:Optimized models
		desc:These more efficient models will cut printing time in half.<//><.>Multiplies yield of 3D printers by <b>2</b>.
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:1750000 peanutCups
		passive:multiply yield of printers by 2
		req:10 printers:max
	*biggerFeeder
		name:Bigger material feeder
		desc:With this, you won't need to refill your printer as often.<//><.>Multiplies yield of 3D printers by <b>2</b>.
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:17500000 peanutCups
		passive:multiply yield of printers by 2
		req:25 printers:max
	*biggerPrinthead
		name:Bigger printhead
		desc:Your printers can squirt out more stuff at once.<//><.>Multiplies yield of 3D printers by <b>4</b>.<.><i>End of tier 1</i>
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:175000000 peanutCups
		passive:multiply yield of printers by 2
		req:50 printers:max

	//PUKER UPGRADES
	
	*largeStomach
		name:Large stomach
		desc:Pukers can hold more peanut butter and chocolate in their stomach.<//><.>Multiplies yield of cup pukers by <b>2</b>.
		cost:2000000 peanutCups
		req:1 cupVomiter:max
		passive:multiply yield of cupVomiter by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
	*fastDigestion
		name:Fast digestion
		desc:Pukers digest faster.<//><.>Multiplies yield of cup pukers by <b>2</b>.
		cost:20000000 peanutCups
		req:10 cupVomiters:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		passive:multiply yield of cupVomiter by 2
	*defecation
		name:Defecation
		desc:Even more gross. Still safe, though. Probably.<//><.>Multiplies yield of cup pukers by <b>2</b>.
		cost:200000000 peanutCups
		req:25 cupVomiters:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		passive:multiply yield of cupVomiter by 2
	*inhale
		name:Inhale ability
		desc:Sucks in the peanut butter and chocolate.<.>Multiplies yield of cup pukers by <b>4</b>.<.><i>End of tier 1</i>
		cost:2000000000 peanutCups
		req:50 cupVomiters:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		passive:multiply yield of cupVomiter by 4

	//REARRANGER UPGRADES

	*breakdown
		name:Molecular breakdown
		desc:Breaking down molecules makes them easier to rearrange.<//><.>Multiplies yield of molecular rearrangers by <b>2</b>.
		cost:25000000 peanutCups
		req:1 rearranger:max
		passive:multiply yield of rearranger by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*noclip
		name:I accidentally left this name as a placeholder for a long time so I'll just leave this here as a monument to my forgetfulness
		desc:At least I won't have to think of a name now.<//><.>Multiplies yield of molecular rearrangers by <b>2</b>.
		cost:250000000 peanutCups
		req:10 rearrangers:max
		passive:multiply yield of rearranger by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*chocolateMolecules
		name:Chocolate molecules
		desc:Chocolate can now be made with a single type of molecule.<//><.>Multiplies yield of molecular rearrangers by <b>2</b>.
		cost:2500000000 peanutCups
		req:25 rearrangers:max
		passive:multiply yield of rearranger by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*quantumTunneling
		name:Quantum tunneling
		desc:Molecules go straight through each other.<.>Multiplies yield of molecular rearrangers by <b>4</b>.<.><i>End of tier 1</i>
		cost:25000000000 peanutCups
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
		req:50 rearrangers:max
		passive:multiply yield of rearranger by 4

	//SHIP UPGRADES
	
	*betterBargaining
		name:Better bargaining
		desc:Best I can do is 20 peanut butter cups.<//><.>Multiplies yield of trade spaceships by <b>2</b>.
		cost:300000000 peanutCups
		req:1 rocketShip:max
		passive:multiply yield of rocketShip by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*hotDeals
		name:Hot deals
		desc:50% off!<//><.>Multiplies yield of trade spaceships by <b>2</b>.
		cost:3000000000 peanutCups
		req:10 rocketShips:max
		passive:multiply yield of rocketShip by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*memberCard
		name:Membership card
		desc:Get rewarded for your loyalty.<//><.>Multiplies yield of trade spaceships by <b>2</b>.
		cost:30000000000 peanutCups
		req:25 rocketShips:max
		passive:multiply yield of rocketShip by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*hyperDrive
		name:Hyperdrive
		desc:The key to fast, efficient space travel.<//><.>Multiplies yield of trade spaceships by <b>4</b>.<.><i>End of tier 1</i>
		cost:300000000000 peanutCups
		passive:multiply yield of rocketShip by 4
		req:50 rocketShips:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*scams
		name:Scams
		desc:The worst trade deals in the history of trade deals.<.>Trade spaceships use <b>20%</b> less chocolate and peanut butter.
		cost:3000000000000 peanutCups
		passive:multiply yield of rocketShip by 4
		req:50 rocketShips:max
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg

	//PORTAL UPGRADES

	*fasterPortals
		name:Faster portals
		desc:Skip the cutscene for going through a portal.<//><.>Multiplies yield of portals by <b>2</b>.
		cost:3250000000 peanutCups
		req:1 cupPortal:max
		passive:multiply yield of cupPortal by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*betterDimension
		name:Better dimension
		desc:Turns out whatever was in that other dimension was slacking off.<//><.>Multiplies yield of portals by <b>2</b>.
		cost:32500000000 peanutCups
		req:10 cupPortals:max
		passive:multiply yield of cupPortal by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*theCake
		name:The cake
		desc:It's a lie. This is the pinnacle of low-hanging fruit.<.>Multiplies yield of portals by <b>2</b>.
		cost:325000000000 peanutCups
		req:25 cupPortals:max
		passive:multiply yield of cupPortal by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*fourthDimension
		name:Fourth dimension
		desc:The thrilling sequel to the third dimension.<.>Multiplies yield of portals by <b>4</b>.<.><i>End of tier 1</i>
		cost:3250000000000 peanutCups
		req:50 cupPortals:max
		passive:multiply yield of cupPortal by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*multiDimensional
		name:Multidimensional portals
		desc:Send peanut butter and chocolate to multiple dimensions at the same time.<.>Multiplies yield of portals by <b>3</b>.
		cost:32500000000000 peanutCups
		req:75 cupPortals:max
		passive:multiply yield of cupPortal by 3
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*portalGuns
		name:Portal guns
		desc:More convenient, as long as you can find a matte white surface nearby.<.>Multiplies yield of portals by <b>3</b>.
		cost:325000000000000 peanutCups
		req:100 cupPortals:max
		passive:multiply yield of cupPortal by 3
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
/*
	*voidPortal
		name:Void portals
		desc:A bunch of peanut butter and chocolate, send it to the void... and get it turned into peanut butter cups.<.>Multiplies yield of portals by <b>3</b>.
		cost:3250000000000000 peanutCups
		req:100 cupPortals:max
		passive:multiply yield of cupPortal by 3
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
*/

	//MYSTERY BOX UPGRADES
	
	*biggerBoxes
		name:Bigger boxes
		desc:We're gonna need a bigger box?<//><.>Multiplies yield of mystery boxes by <b>2</b>.
		cost:35000000000 peanutCups
		req:1 mysteryBox:max
		passive:multiply yield of mysteryBox by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*addedMystery
		name:Added mystery
		desc:The suspense is killing me.<//><.>Multiplies yield of mystery boxes by <b>2</b>.
		cost:350000000000 peanutCups
		req:10 mysteryBoxes:max
		passive:multiply yield of mysteryBox by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*schrodingersCat
		name:Schrodinger's cat
		desc:Just hangs out in the mystery box with your peanut butter and chocolate.<.>Multiplies yield of mystery boxes by <b>2</b>.
		cost:3500000000000 peanutCups
		req:25 mysteryBoxes:max
		passive:multiply yield of mysteryBox by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*boxSquared
		name:Mystery box²
		desc:Send mystery boxes full of peanut butter cups through other mystery boxes.<.>Multiplies yield of mystery boxes by <b>4</b>.<.><i>End of tier 1</i>
		cost:35000000000000 peanutCups
		req:50 mysteryBoxes:max
		passive:multiply yield of mysteryBox by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*reinforcedBoxes
		name:Reinforced boxes
		desc:That flimsy cardboard won't do.<.>Multiplies yield of mystery boxes by <b>3</b>.
		cost:350000000000000 peanutCups
		req:75 mysteryBoxes:max
		passive:multiply yield of mysteryBox by 3
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg

	//SUBATOMIC UPGRADES

	*bingBong
		name:Bing bong theory
		desc:Bazoomba<//><.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>2</b>.
		cost:400000000000 peanutCups
		req:1 subAtomics:max
		passive:multiply yield of mysteryBox by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*ropeTheory
		name:Rope theory
		desc:Because strings are far too small.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>2</b>.
		cost:4000000000000 peanutCups
		req:10 subAtomics:max
		passive:multiply yield of mysteryBox by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*scientificScience
		name:Scientific science
		desc:It just wasn't quite scientific enough before.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>2</b>.
		cost:40000000000000 peanutCups
		req:25 subAtomics:max
		passive:multiply yield of mysteryBox by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*subsubAtomic
		name:Subsubatomic particles
		desc:What <i>really</i> makes up the universe.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>4</b>.<.><i>End of tier 1</i>
		cost:400000000000000 peanutCups
		req:50 subAtomics:max
		passive:multiply yield of mysteryBox by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*superConvapitator
		name:Supercharged convapitators
		desc:Although the subatomic moleculization is an important part of the convapitation process, it all falls apart if the convapitators themselves can't convapitate well enough.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>3</b>.
		cost:4000000000000000 peanutCups
		req:75 subAtomics:max
		passive:multiply yield of mysteryBox by 3
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*molecularSubitizer
		name:Molecular subatomicizers
		desc:Pull the ol' switcheroo.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>3</b>.
		cost:40000000000000000 peanutCups
		req:100 subAtomics:max
		passive:multiply yield of mysteryBox by 3
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg

	//EXTRACTOR UPGRADES
	
	*suckierHoles
		name:Suckier holes
		desc:uhh<.>Multiplies yield of black hole extractors by <b>2</b>.
		cost:6789012345670 peanutCups
		req:1 bhExtractor:max
		passive:multiply yield of bhExtractor by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*eventfulHorizons
		name:More eventful horizons
		desc:Action-packed!<.>Multiplies yield of black hole extractors by <b>2</b>.
		cost:67890123456701 peanutCups
		req:10 bhExtractors:max
		passive:multiply yield of bhExtractor by 2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*antiSpaghetti
		name:Spaghettification prevention
		desc:Do I make a "hope she made lotsa spaghetti" joke or a "somebody toucha my spaghet" joke? Or will both of these jokes eventually be long forgotten and make my game dated?<.>Multiplies yield of black hole extractors by <b>2</b>.
		cost:678901234567012 peanutCups
		req:25 bhExtractors:max
		passive:multiply yield of bhExtractor by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*galacticCores
		name:Galactic cores
		desc:As some of the most massive black holes in the universe, these can have entire galaxies orbiting them. They should do the trick.<.>Multiplies yield of black hole extractors by <b>4</b>.<.><i>End of tier 1</i>
		cost:6789012345670123 peanutCups
		req:50 bhExtractor:max
		passive:multiply yield of bhExtractor by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*compactDisks
		name:Compact accretion disks
		desc:Way better than the floppy ones.<.>Multiplies yield of black hole extractors by <b>3</b>.
		cost:67890123456701234 peanutCups
		req:75 bhExtractor:max
		passive:multiply yield of bhExtractor by 3
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg

	//ANOMALY UPGRADES

	*longRange
		name:Long-range anomalies
		desc:Convert things from <i>coast to coast</i>.<.>Multiplies yield of space-time anomalies by <b>2</b>.
		cost:115000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:1 anomaly:max
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*blindSpots
		name:Blind spots
		desc:Wow, you're so insensitive (to light)<.>Multiplies yield of space-time anomalies by <b>2</b>.
		cost:1150000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:10 anomalies:max
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*loweredFOV
		name:Lowered FOV
		desc:I'm sure no one will notice.<.>Multiplies yield of space-time anomalies by <b>2</b>.
		cost:11500000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:25 anomalies:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*instantConversion
		name:Instant conversion
		desc:The mere blink of an eye could get your peanut butter and chocolate converted!<.>Multiplies yield of space-time anomalies by <b>4</b>.<.><i>End of tier 1</i>
		cost:115000000000000000 peanutCups
		passive:multiply yield of anomalies by 4
		req:50 anomalies:max
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg

	//PRESTIGE UPGRADES

	*TEMPLATE
		class:smallThing thing
		on click:
			if (clickAnimation=1)
				anim icon wobble2
				anim wobble2
			end
			if (clickAnimation=2)
				anim icon bounceOnce
				anim bounceOnce
			end
			if (clickAnimation=3)
				anim icon plop
				anim plop
			end
			if (clickAnimation=4)
				anim icon wiggling2
				anim wiggling
			end
			if (clickAnimation=5)
				anim icon wobbleSlow
				anim wobbleSlow
			end
		end
		tag:divine
		class:divine
		no text

	*prestige1
		name:A world of peanut butter cups
		desc:Your ultimate goal is to fill the multiverse with peanut butter cups. Fill this small universe and move on to a larger one.</><i>You will:</i><.>Leave behind <b>all</b> buildings, resources, upgrades, and secrets.<.>Gain <b>150</b> divine peanut butter cups to be used to purchase upgrades and get boosts.<.>Unlock the next tier of buildings (and the next tier of upgrades will come eventually)
		on earn:lose tag:upgrade
		on earn:lose :Buildings
		on earn:lose tag:resource
		on earn:lose tag:special
		on earn:lose tag:secret
		on earn:lose tag:secretPoints
		on earn:yield 150 divineCups
		on earn:yield (peanutCups:earned) leftBehind
		on earn:yield (chocolate:earned) cleftBehind
		on earn:yield (peanutButter:earned) pleftBehind
		on earn:yield 1 manaThing
		on earn:yield 1 aaa
		on earn:ownedUpgradetxt=0
		cost:50e12 peanutCups
		icon:https://cdn.rawgit.com/morkysherk/84b3fcfc17d8147fe14be41776811256/raw/726420cb188cac9487c94ff14cdb4c0799e3f86a/space.svg
	*angelicCuppersUnlock
		name:Angelic cuppers
		desc:Unlocks <b>angelic cuppers</b> to unleash the power of your divine cups.
		passive:multiply yield of tag:philding by (((pow(1.0002,angelicCuppers)-1)*(divineCups:earned))+1)
		cost:50 divineCups
	 icon:https://cdn.rawgit.com/morkysherk/b914a55433f5e3af3bab7b6d6641b29a/raw/15883d5279e720636ae9e91e83fdf33cd710055d/divinecup.svg
		req:prestige1
	*divineMult
		name:Divine multiplier
		desc:Instantly adds <b>25%</b> to your multiplier.
		passive:multiply yield of tag:philding by 1.25
		cost:25 divineCups
	   icon:https://cdn.rawgit.com/morkysherk/86d070b4516e9992155d38da2000a70f/raw/c996146b624bff280a70cb3a5dedda22ba45d321/divinex.svg
		req:prestige1
	*goldPiggy
		name:Golden piggy bank
		desc:oink oink<.>You will keep <b>20%</b> of your golden beans, crystal beans, bean pods, and spell boost levels in the next universe.
		cost:25 divineCups
		icon:https://cdn.rawgit.com/morkysherk/7b575ecf5e9917cc33a001f8299f97ed/raw/c68134ef4502d80a289bf0917da05f748e638d01/gpiggy.svg
		req:prestige1
	*goldCoupon
		name:Golden coupon
		desc:Worth quite a bit more than its weight in gold.<.>Gives you a <b>33%</b> discount on all golden bean upgrades, including spell boosts.
	   icon:https://cdn.rawgit.com/morkysherk/df919b41f3879683f11ea009956680cd/raw/fe1570bd5593bf9800960357662b1d5335f024b2/gCoupon.svg
		passive:multiply cost of tag:beanUpgrade by 0.67
		req:prestige1
	*cheaperBuildings
		name:Cheaper buildings
		desc:I like m̶o̶n̶e̶y̶ peanut butter cups<.>Gives a <b>5%</b> discount on all upgrades.
		passive:multiply cost of tag:upgrade by 0.95
		cost:25 divineCups
	   icon:https://cdn.rawgit.com/morkysherk/444b6e9db0490f9c886f22af83fa5483/raw/a3537a38ca99d063aefc37232e2c64096a8e7784/saletag.svg
		req:prestige1
	*extraBrittle
		name:Extra-brittle shells
		desc:Spells open <b>67%</b> more golden bean pods.

	//PURCHASED UPGRADES


	*TEMPLATE
		class:thing
		on click:
			if (clickAnimation=1)
				anim icon wobble2
				anim wobble2
			end
			if (clickAnimation=2)
				anim icon bounceOnce
				anim bounceOnce
			end
			if (clickAnimation=3)
				anim icon plop
				anim plop
			end
			if (clickAnimation=4)
				anim icon wiggling2
				anim wiggling
			end
			if (clickAnimation=5)
				anim icon wobbleSlow
				anim wobbleSlow
			end
		end
		tag:upgradeOwned
		no buy
		no text

	//RECIPES

	*cupRecipeO
		name:Peanut butter cup recipe
		desc:Discover the ancient secrets of cupping peanut butter.<//><.>Unlocks peanut butter cup producers.
		req:cupRecipe
		icon:https://cdn.rawgit.com/morkysherk/0cdaa3a1509eb96be2bf37b4de20a0cd/raw/831ea35eca9b0eb008c038d929f7b3a112da4f2f/scroll.svg

	//GOLD BEAN UPGRADES

	*fourcloverLeafO
		name:Four clover leaf
		desc:Four leaf clovers may be rare, but has anyone ever seen one of these?<//><.>Golden peanut butter cups will appear <b>10%</b> more often.<.>Golden peanut butter cups will require <b>10</b> less mana to summon.
		passive:multiply frequency of luckyCup by 0.9
		cost:100 goldBeans
		req:7 lclicks
		req:fourcloverLeaf
		icon:https://imgur.com/XGcyejq.png
	*luckyBoostO
		name:Tiny lucky boost
		desc:Use the power of a small bit of luck to your benefit.<//><.>Boosts all production by <b>1%</b>.
		cost:100 goldBeans
		req:7 lclicks
		passive:multiply yield of tag:building by 1.03
		on earn:yield (multiplier*0.01) multiplier
		req:luckyBoost
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
	*podSummonBoostO
		name:Golden bean pod summoning boost
		desc:Get <b>5</b> golden bean pods per "Spawn golden bean pod" cast instead of 1.
		cost:500 goldBeans
		req:7 lclicks
		req:podSummonBoost
		icon:numbers[0,0] https://cdn.rawgit.com/morkysherk/794ef2cdfe99067dbec1c51f648e7054/raw/baf44aa7a9184b35dda5080a758ffeabe9702947/pod.svg
	*blackcatHorseshoeO
		name:Black cat's horseshoe
		desc:Just don't let it cross your path.<//><.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15</b> less mana to summon.<.>Golden peanut butter cups will have slightly boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:1000 goldBeans
		cost:1 crystalBean
		req:10 lclicks
		req:blackcatHorseshoe
	icon:https://cdn.rawgit.com/morkysherk/9c6691e4d32e6a90df9b98214453bc89/raw/a947c17d45a345c4c2e458f61fd454a21e074a0a/blackcatHorseshoe.svg
	*smallLuckyBoostO
		name:Relatively small lucky boost
		desc:Use the power of a little more luck to your benefit.<//><.>Boosts all production by <b>1.5%</b>.
		cost:1000 goldBeans
		cost:1 crystalBean
		req:10 lclicks
		passive:multiply yield of tag:building by 1.015
		on earn:yield (multiplier*0.015) multiplier
		req:smallLuckyBoost
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
	*halfRainbowO
		name:Half Rainbow
		desc:Halfway across the sky!<//><.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15<b> less mana to summon.<.>Golden peanut butter cups will have moderately boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:5000 goldBeans
		cost:3 crystalBeans
		req:17 lclicks
		req:halfRainbow
	icon:https://cdn.rawgit.com/morkysherk/39a168e26cc819f1ad359d3dc22ea8c1/raw/848323dde50f89f9199012ed70644b4b9df66bd6/halfRainbow.svg
	*fairlyLuckyBoostO
		name:Fairly lucky boost
		desc:Use the power of a fair bit of luck to your benefit.<//><.>Boosts all production by <b>2%</b>.
		cost:5000 goldBeans
		cost:3 crystalBeans
		req:17 lclicks
		passive:multiply yield of tag:building by 1.02
		on earn:yield (multiplier*0.02) multiplier
		req:fairlyLuckyBoost
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
	*closedUmbrellaO
		name:Closed umbrella
		desc:Keep it inside.<//><.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15<b> less mana to summon.<.>Golden peanut butter cups will have boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:20000 goldBeans
		cost:10 crystalBeans
		req:37 lclicks
		req:closedUmbrella
	icon:https://cdn.rawgit.com/morkysherk/61ef6c72d66f667cc67f8046a86dd747/raw/5ec7158eba2de361820a4fa2a3ebfc26dbb90049/closedUmbrella.svg
	*sizableLuckyBoostO
		name:Sizable lucky boost
		desc:Use the power of a decent amount of luck to your benefit.<//><.>Boosts all production by <b>2.5%</b>.
		cost:20000 goldBeans
		cost:10 crystalBeans
		req:37 lclicks
		passive:multiply yield of tag:building by 1.02
		on earn:yield (multiplier*0.02) multiplier
		req:sizableLuckyBoost
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/d13f4ab63187a47e25b777bb2cffe748/raw/cdfa1b70b3acc448b7104559df24b096ae01cc45/gBean.svg
		passive:multiply yield of tag:building by 1.025
		on earn:yield (multiplier*0.025) multiplier
	*d7O
		name:7 sided die
		desc:Just the right amount of rigged.<.>Golden peanut butter cups will appear another <b>10%</b> more often and cost another <b>15</b> less mana to summon.<.>Golden peanut butter cups will have more boosted effects.
		passive:multiply frequency of luckyCup by 0.9
		cost:100000 goldBeans
		cost:50 crystalBeans
		req:57 lclicks
		req:d7
		icon:https://cdn.rawgit.com/morkysherk/0cba993d0942bc96e859120ddb03bc6e/raw/6d495d3d593523d9d8cbad59113f0c3277f2a131/d7.svg
	
	//RESOURCE CLICKING

	*peanutcupClickingO
		name:Peanut Butter Cup Clicking
		desc:Clicking either button 3 times will produce a peanut butter cup.
		cost:1000 peanutCups
		req:1 peanutCup:ps
		req:notaButton
		req:peanutcupClicking
		icon:https://imgur.com/Pu0f5pK.png
	*combinedClickingO
		name:Combined Clicking
		desc:Clicking the chocolate twice will produce a jar of peanut butter, and vice versa.
		cost:10000 chocolate
		cost:10000 peanutButter
		req:1000 chocoButton clicks
		req:1000 pButton clicks
		req:combinedClicking
		icon:https://imgur.com/kTtlgRR.png

	//BETTER BUTTON UPGRADES

	*betterButtonO
		name:Better Button
		desc:Now with 100% more!<//><.>The peanut butter button will produce <b>twice</b> as much peanut butter, and the chocolate button will yield <b>twice</b> as much chocolate.<.>Multiplies yield of autoclickers by <b>2</b>.
		cost:100 chocolate
		cost:100 peanutButter
		passive:multiply chocolate yield of chocoButton by 2
		passive:multiply peanutButter yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2
		passive:multiply peanutButter yield of clicker by 2
		req:1 chocolate:earned
		req:betterButton
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*betterButton2O
		name:Better Button II
		desc:Just compare it to the leading brand!<//><.>The peanut butter button will produce <b>twice</b> as much peanut butter, and the chocolate button will yield <b>twice</b> as much chocolate.<.>Multiplies yield of autoclickers by <b>2</b>.
		cost:1000 chocolate
		cost:1000 peanutButter
		passive:multiply chocolate yield of chocoButton by 2
		passive:multiply peanutButter yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2
		passive:multiply peanutButter yield of clicker by 2
		req:betterButton2
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*betterButton3O
		name:Better Button III
		desc:We'll double the offer!<//><.>Multiplies all yield of buttons by <b>2</b>.<.>Multiplies yield of clickers by <b>2.25</b>.
		cost:5000 chocolate
		cost:5000 peanutButter
		cost:1000 peanutCups
		req:betterButton3
		passive:multiply yield of chocoButton by 2
		passive:multiply yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2.25
		passive:multiply peanutButter yield of clicker by 2.25
		passive:multiply goldBeanPod yield of clicker by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*betterButton4O
		name:Better Button IV
		desc:But wait, there's more!<//><.>Multiplies yield of buttons by <b>2</b>.<.>Multiplies yield of clickers by <b>2.5</b>.
		cost:50000 chocolate
		cost:50000 peanutButter
		cost:25000 peanutCups
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply yield of chocoButton by 2
		passive:multiply yield of pButton by 2
		passive:multiply chocolate yield of clicker by 2.5
		passive:multiply peanutButter yield of clicker by 2.5
		passive:multiply goldBeanPod yield of clicker by 2
		req:betterButton4
	*betterButton5O
		name:Better Button V
		desc:Call now and you'll receive a mini button too!<//><.>Clicking either button will produce <b>7.5%</b> more chocolate, peanut butter, and peanut butter cups per chocolate worker and peanut butterer.<.>Multiplies yield of autoclickers by <b>2.75</b>.
		cost:500000 chocolate
		cost:500000 peanutButter
		cost:300000 peanutCups
		icon:numbers[5,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply chocolate yield of chocoButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply chocolate yield of pButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutButter yield of chocoButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutButter yield of pButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutCup yield of chocoButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply peanutCup yield of pButton by (1+((chocolateWorkers+peanutButterers)*0.075))
		passive:multiply chocolate yield of clicker by 2.75
		passive:multiply peanutButter yield of clicker by 2.75
		req:betterButton5
	*betterButton6O
		name:Better Button VI
		desc:Are you tired of this? <i>clicks button and gets nothing</i><//><.>Clicking either button will produce <b>15%</b> more chocolate, peanut butter, and peanut butter cups per chocolate farm and peas and nuts converter.<.>Combined and peanut butter cup clicking are twice as effective.<.>Multiplies yield of autoclickers by <b>3</b>.
		cost:5000000 chocolate
		cost:5000000 peanutButter
		cost:3000000 peanutCups
		icon:numbers[6,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply chocolate yield of chocoButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply chocolate yield of pButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutButter yield of chocoButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutButter yield of pButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutCup yield of chocoButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply peanutCup yield of pButton by (1+((refineries+pbFactories)*0.15))
		passive:multiply chocolate yield of pButton by 2
		passive:multiply peanutButter yield of chocoButton by 2
		passive:multiply peanutCup yield of pButton by 2
		passive:multiply peanutCup yield of chocoButton by 2
		passive:multiply chocolate yield of clicker by 3
		passive:multiply peanutButter yield of clicker by 3
		req:betterButton6
	*betterButton7O
		name:Better Button VII
		desc:Woops, looks like I'm all out of ideas.<.>Clicking either button will produce <b>22.5%</b> more chocolate, peanut butter, and peanut butter cups per refinery and factory.<.>Multiplies yield of autoclickers by <b>3.25</b>.
		cost:500000000 chocolate
		cost:500000000 peanutButter
		cost:300000000 peanutCups
		icon:numbers[7,0] https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
		passive:multiply chocolate yield of chocoButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply chocolate yield of pButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutButter yield of chocoButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutButter yield of pButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutCup yield of chocoButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply peanutCup yield of pButton by (1+((chocoFarms+factories)*0.225))
		passive:multiply chocolate yield of clicker by 3.25
		passive:multiply peanutButter yield of clicker by 3.25
		req:betterButton7

	//CUP TYPES

	*darkCupsO
		name:Dark chocolate peanut butter cups
		desc:These more bitter cups will balance out the sweet peanut butter, and add <b>2%</b> to your production multiplier.
		cost:10000 peanutCups
		passive:multiply yield of tag:building by 1.02
		on earn:yield (multiplier*0.02) multiplier
		req:1000 peanutCups:earned
		req:darkCups
	   icon:https://cdn.rawgit.com/morkysherk/cc542868ef20cfc9b7423346a66a808b/raw/5e6f2c64dcd5f775fe7cc77248c856a4cdf39c11/dankCup.svg
	*whiteCupsO
		name:White chocolate peanut butter cups
		desc:These cups will add another <b>3%</b> to your production multiplier.
		passive:multiply yield of tag:building by 1.03
		on earn:yield (multiplier*0.03) multiplier
		cost:100000 peanutCups
		req:10000 peanutCups:earned
		req:whiteCups
		icon:https://cdn.rawgit.com/morkysherk/d62cf2cc2aa0ff9bb14820ac32ecf6b4/raw/629d7d32e5c0224ffc69f1eff0a76bba492e01c2/white.svg
	*miniCupsO
		name:Mini Peanut Butter Cups
		desc:These tiny peanut butter cups will go a long way by adding <b>5%</b> to your production multiplier.
		passive:multiply yield of tag:building by 1.05
		on earn:yield (multiplier*0.05) multiplier
		cost:10000000 peanutCups
		req:1000000 peanutCups:earned
		req:miniCups
		icon:https://cdn.rawgit.com/morkysherk/c535202fb639a334a9e92a9f742823f1/raw/e11ecf49f7fd4f7407e26eea00445bd645e308ed/mini.svg
	*cookieCupsO
		name:Cookies n' Creme Peanut ButterCups
		desc:Combine the addicting flavor or cookies and creme with the divine taste of peanut butter cups to earn another <b>+5%</b> to your production multiplier.
		passive:multiply yield of tag:building by 1.05
		on earn:yield (multiplier*0.05) multiplier
		req:100000000 peanutCups:earned
		cost:1000000000 peanutCups
		req:cookieCups
		icon:https://cdn.rawgit.com/morkysherk/448400d1ea3175f67a88555781cd44dc/raw/bee0e63623a77f7dbb8fcdabd7e5c2ecb0baf53c/ccCup.svg

	//ACHIEVEMENT BONUSES
		
	*whiteRibbonO
		name:White Ribbon
		desc:3rd...<.>Increases your multiplier by <b>0.5%</b> per achievement earned.
		cost:1000000 peanutCups
		cost:1000000 chocolate
		cost:1000000 peanutButter
		req:whiteRibbon
	   icon:https://cdn.rawgit.com/morkysherk/c261f5c738d6b695d9af0bfd0f4dfd47/raw/7f0e2dc43469121e2c6bda2ac259a221e77ea5cc/ribbon3.svg
		passive:multiply yield of tag:building by (1+(0.005*(achievPoints)))
	*redRibbonO
		name:Red Ribbon
		desc:2nd...<.>Increases your multiplier by <b>0.75%</b> per achievement earned.
		cost:10000000000 peanutCups
		cost:10000000000 chocolate
		cost:10000000000 peanutButter
		req:redRibbon
	   icon:https://cdn.rawgit.com/morkysherk/3dbf8f73ce882152bbdf5078ffcf4262/raw/2e3a0f05291acecc7e3dacce36b9da723b0c4642/ribbon2.svg
		passive:multiply yield of tag:building by (1+(0.0075*(achievPoints)))
	*blueRibbonO
		name:Blue Ribbon
		desc:1st place!<.>Increases your multiplier by <b>1%</b> per achievement earned.
		cost:100000000000000 peanutCups
		cost:100000000000000 chocolate
		cost:100000000000000 peanutButter
		req:blueRibbon
	   icon:https://cdn.rawgit.com/morkysherk/8d46797cc8e4ddecab5bd6f5e4326ed0/raw/4d6e564c983317170c40b6915f17ecee8c8225f6/ribbon1.svg
		passive:multiply yield of tag:building by (1+(0.01*(achievPoints)))

	//OTHER

	*gainfulPainO
		name:Gainful pain
		desc:oof<.>Boosts peanut butter cup production by <b>50%</b> when chocolate or peanut butter production is negative.
		req:loss
		on tick:
			if (peanutButter:ps<0 or chocolate:ps<0)
				yield (peanutCups:ps/2) peanutCups
			end
		end
		req:gainfulPain
		icon:https://cdn.rawgit.com/morkysherk/22804416129794044b726fc47b0ab198/raw/c4683db1a1002a50fb139d41c770cb02405c21cd/+-.svg
			

	//WORKER UPGRADES

	*trainingO
		name:Training
		desc:Trained workers just might be more efficient.<//><.>Chocolate workers, peanut butterers, and peanut butter cuppers are <b>50%</b> faster.
		cost:1000 chocolate
		cost:1000 peanutButter
		cost:500 peanutCups
		req:10 chocolateWorkers:max
		req:10 peanutButterers:max
		req:1 peanutCupper:max
		passive:multiply yield of chocolateWorkers by 1.5
		passive:multiply yield of peanutButterers by 1.5
		passive:multiply yield of peanutCuppers by 1.5
		req:training
	    icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/3e0ec7b2a12853b346b0a51c1758592d/raw/017fbaa567ab0c82a2ac5dea0ab4e1ab60bf38b8/gradCap.svg
	*collegeEducationO
		name:Working smarter
		desc:Not harder.<//><.>Chocolate workers, peanut butterers, and peanut butter cuppers are <b>50%</b> faster.
		cost:10000 chocolate
		cost:10000 peanutButter
		cost:100 peanutCups
		req:25 chocolateWorkers:max
		req:25 peanutButterers:max
		req:10 peanutCuppers:max
		passive:multiply yield of chocolateWorkers by 1.5
		passive:multiply yield of peanutButterers by 1.5
		passive:multiply yield of peanutCuppers by 1.5
		req:collegeEducation
	    icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/3e0ec7b2a12853b346b0a51c1758592d/raw/017fbaa567ab0c82a2ac5dea0ab4e1ab60bf38b8/gradCap.svg
	*collegeEducationAO
		name:College education
		desc:I have a PhD in making peanut butter cups.<//><.>Chocolate workers, peanut butterers, and peanut butter cuppers are <b>50%</b> faster.
		cost:100000 chocolate
		cost:100000 peanutButter
		cost:1000 peanutCups
		req:50 chocolateWorkers:max
		req:50 peanutButterers:max
		req:25 peanutCuppers:max
		passive:multiply yield of chocolateWorkers by 1.5
		passive:multiply yield of peanutButterers by 1.5
		passive:multiply yield of peanutCuppers by 1.5
		req:collegeEducationA
	    icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/3e0ec7b2a12853b346b0a51c1758592d/raw/017fbaa567ab0c82a2ac5dea0ab4e1ab60bf38b8/gradCap.svg

	//CHOCOLATE WORKER UPGRADES	

	*fasterRoastingO
		name:Faster roasting
		desc:Chocolate workers roast cocoa beans faster.<//><.>Multiplies yield of chocolate workers by <b>2</b>.
		cost:500 chocolate
		req:1 chocolateWorker:max
		passive:multiply yield of chocolateWorker by 2
		req:fasterRoasting
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*literalchocoWorkersO
		name:Literal chocolate workers
		desc:Chocolate workers are now made of chocolate, which makes them faster. Don't ask.<//><.>Multiplies yield of chocolate workers by <b>2</b>.
		cost:5000 chocolate
		req:10 chocolateWorker:max
		passive:multiply yield of chocolateWorker by 2
		req:literalchocoWorkers
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*mitosisO
		name:Higher melting point
		desc:You've run into some problems with melting workers.<//><.>Multiplies yield of chocolate workers by <b>2</b>.
		cost:50000 chocolate
		passive:multiply yield of chocolateWorker by 2
		req:25 chocolateWorkers:max
		req:mitosis
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*mitosis1O
		name:Mitosis
		desc:why do i have to give birth why can't i just do my toast is<//><.>Multiplies yield of chocolate workers by <b>4</b>.<.><i>End of tier 1</i>
		cost:500000 chocolate
		passive:multiply yield of chocolateWorker by 4
		req:50 chocolateWorkers:max
		req:mitosis1
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*reinforcedWorkersO
		name:Reinforced chocolate workers
		desc:Industrial strength.<.>Multiplies yield of chocolate workers by <b>3</b>.<.>
		cost:5000000 chocolate
		passive:multiply yield of chocolateWorker by 3
		req:75 chocolateWorkers:max
		req:reinforcedWorkers
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
	*whiteChocoWorkersO
		name:White chocolate workers
		desc:The sweetest little guys you've ever met. Also pretty creamy.<.>Multiplies yield of chocolate workers by <b>3</b>.<q>white supremacist idle game makes the white workers better!! wee woo wee woo sound the alarm!</q>
		cost:50000000 chocolate
		passive:multiply yield of chocolateWorker by 3
		req:100 chocolateWorkers:max
		req:whiteChocoWorkers
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
/*
	*bronzeChocoBarO
		name:Bronze chocolate bar
		cost:1500 goldBeans
		desc:a feature
		req:bronzeChocoBar
	icon:https://cdn.rawgit.com/morkysherk/bc9dc27462ac807b80357f97ee30c6c2/raw/3bbc191e569ad8ca197bea308d80c1042effbb8e/chocobarbronze.svg
	*silverChocoBarO
		name:Silver chocolate bar
		cost:4500 goldBeans
		desc:a feature
		req:silverChocoBar
	icon:https://cdn.rawgit.com/morkysherk/652c6258f895bc341b2877edcf47977b/raw/2410a9706e8b7a5c627d1b6527fa919661d929b6/chocsilver.svg
	*goldChocoBarO
		name:Golden chocolate bar
		cost:22500 goldBeans
		desc:a feature
		req:goldChocoBar
	  icon:https://cdn.rawgit.com/morkysherk/2f3779e36d4e51dcf119f736965c23b0/raw/d0c182746840fa50103223f9ae0282d9a4fcddfa/chocgold.svg
	*crystalChocoBarO
		name:Crystal chocolate bar
		cost:157500 goldBeans
		desc:a feature
		req:crystalChocoBar
	icon:https://cdn.rawgit.com/morkysherk/7836391057ed4ceea8946de1d042bb58/raw/f22300d877fdff866df64b911bf6a125e73edefb/choccrystal.svg
*/

	//FARM UPGRADES

	*refinedRefineriesO
		name:Fertilizer
		desc:Enhance your trees' growth rates.<//><.>Multiplies yield of farms by <b>2</b>.
		cost:7500 chocolate
		passive:multiply yield of refinery by 2
		req:refinedRefineries
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:1 refinery:max
	*fasterGrindersO
		name:Healthier seeds
		desc:Make them healthier before they even start growing.<//><.>Multiplies yield of farms by <b>2</b>.
		cost:75000 chocolate
		passive:multiply yield of refinery by 2
		req:fasterGrinders
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*extraMixableO
		name:Flavored water
		desc:Drinking regular water every day must get boring.<//><.>Multiplies yield of farms by <b>2</b>.
		cost:750000 chocolate
		passive:multiply yield of refinery by 2
		req:25 refineries:max
		req:extraMixable
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocosynthesisO
		name:Chocosynthesis
		desc:Convert sunlight into chocolate instead of sugar.<.>Multiplies yield of farms by <b>4</b>.<.><i>End of tier 1</i>
		cost:7500000 chocolate
		passive:multiply yield of refinery by 4
		req:50 refineries:max
		req:chocosynthesis
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocoSoilO
		name:Chocolate soil
		desc:Makes walking around the farms a relatively unpleasant experience, but helps your trees grow.<.>Multiplies yield of farms by <b>3</b>.
		cost:75000000 chocolate
		passive:multiply yield of refinery by 3
		req:75 refineries:max
		req:chocoSoil
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
	*chocoWeedsO
		name:Chocolate weeds
		desc:Make those pesky plants into efficient chocolate producers.<.>Multiplies yield of farms by <b>3</b>.
		cost:750000000 chocolate
		passive:multiply yield of refinery by 3
		req:100 refineries:max
		req:chocoWeeds
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
/*
	*bronzePodO
		name:Bronze chocolate pod
		desc:a feature
		icon:https://goo.gl/WzWiuc
		req:bronzePod
	*silverPodO
		name:Silver chocolate pod
		desc:a feature
		icon:https://goo.gl/Po4jnP
		req:silverPod
	*goldPodO
		name:Golden chocolate pod
		desc:a feature
		req:goldPod
		icon:https://goo.gl/TRWfWg
	*crystalPodO
		name:Crystal chocolate pod
		desc:a feature
		req:crystalPod
		icon:https://goo.gl/DtKnZk
*/

	//REFINERY UPGRADES

	*refinedRefineriesAO
		name:Refined refineries
		desc:Refined refineries refine refined-er chocolate.<//><.>Multiplies yield of refineries by <b>2</b>.
		cost:112500 chocolate
		passive:multiply yield of chocoFarm by 2
		req:refinedRefineriesA
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:1 chocoFarm:max
	*fasterGrindersAO
		name:Faster grinders
		desc:griiiiind<//><.>Multiplies yield of refineries by <b>2</b>.
		cost:1125000 chocolate
		passive:multiply yield of chocoFarm by 2
		req:10 chocoFarms:max
		req:fasterGrindersA
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
	*extraMixableAO
		name:Extra mixable cocoa
		desc:The liquid cocoa will mix more quickly with other ingredients.<//><.>Multiplies yield of refineries by <b>2</b>.
		cost:11250000 chocolate
		passive:multiply yield of chocoFarm by 2
		req:25 chocoFarms:max
		req:extraMixableA
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
	*decombobulatorsO
		name:Discombobulators
		desc:An important part of chocolate discombobulation.<//><.>Multiplies yield of refineries by <b>4</b>.<.><i>End of tier 1</i>
		cost:112500000 chocolate
		passive:multiply yield of chocoFarm by 4
		req:decombobulators
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:50 chocoFarms:max
/*
	*bronzeGrinderO
		name:Bronze cocoa grinder
		cost:33750 goldBean
		desc:a feature
		req:bronzeGrinder
  icon:https://cdn.rawgit.com/morkysherk/f4bb8783a31ee0f26b229d614da86e12/raw/8da189e51faf5d5a09960f85452ea49e5d320905/refineBronze.svg
	*silverGrinderO
		name:Silver cocoa grinder
		cost:101250 goldBean
		desc:a feature
		req:silverGrinder
    icon:https://cdn.rawgit.com/morkysherk/facff1cb86ae9dc631304589d09bccd9/raw/c823491e173e9ed1707263ec60faa5449f84ebc2/refineSilv.svg
	*goldenGrinderO
		name:Golden cocoa grinder
		cost:506250 goldBean
		desc:a feature
		req:goldenGrinder
    icon:https://cdn.rawgit.com/morkysherk/4906f4a614109f5551105c11eb41ddc8/raw/a50fd1be5301262a7c2491fa6943f92a23d172ac/refineGold.svg
	*crystalGrinderO
		name:Crystal cocoa grinder
		cost:3543750 goldBean
		desc:a feature
		req:crystalGrinder
   icon:https://cdn.rawgit.com/morkysherk/ddcc9c051ae0c268d6797e0a37bfd2d9/raw/43b09fc67b36888ea0bcea1e978e0a7e327f438d/refineCrys.svg
*/

	//BUTTERER UPGRADES

	*fastProcessorsO
		name:Faster food processors
		desc:Peanut butterers use faster food processors.<//><.>Multiplies yield of peanut butterers by <b>2</b>.
		cost:500 peanutButter
		passive:multiply yield of peanutButterer by 2
		req:1 peanutButterer:max
		req:fastProcessors
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*softerPeanutsO
		name:Softer peanuts
		desc:Peanuts are softer, and can be processed faster.<//><.>Multiplies yield of peanut butterers by <b>2</b>.
		cost:5000 peanutButter
		passive:multiply yield of peanutButterer by 2
		req:10 peanutButterers:max
		req:softerPeanuts
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*biggerProcessorsO
		name:Bigger processors
		desc:More room to shove your peanuts into.<//><.>Multiplies yield of peanut butterers by <b>2</b>.
		cost:50000 peanutButter
		passive:multiply yield of peanutButterer by 2
		req:25 peanutButterers:max
		req:biggerProcessors
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
	*cProcessorsO
		name:Computer processors
		desc:Are you sure these'll work?<//><.>Multiplies yield of peanut butterers by <b>4</b><.><i>End of tier 1</i>
		cost:500000 peanutButter
		passive:multiply yield of peanutButterer by 4
		req:50 peanutButterers:max
		req:cProcessors
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
/*
	*bronzePBO
		name:Bronze peanut butter jar
		cost:1 goldBean
		desc:a feature
		req:bronzePB
	icon:https://cdn.rawgit.com/morkysherk/a0e57a81d36393239966e36d64e0efc0/raw/937e5fc79bbfab264451290e53ea2dc94bd16337/peabBronze.svg
	*silverPBO
		name:Silver peanut butter jar
		cost:1 goldBean
		desc:a feature
		req:silverPB
	icon:https://cdn.rawgit.com/morkysherk/72e2431054895f324d1885b09f0f7217/raw/89adcdd7556ef41476cb97cbfc12ad2aa4daee2a/peabSilver.svg
	*goldPBO
		name:Golden peanut butter jar
		cost:1 goldBean
		desc:a feature
		req:goldPB
	  icon:https://cdn.rawgit.com/morkysherk/b16462a34af30db59724b84a461f19c8/raw/b7f8f57bdf5211b93e0b9e54472e07b6c3e1002d/peabGold.svg
	*crystalPBO
		name:Crystal peanut butter jar
		cost:1 goldBean
		desc:a feature
		req:crystalPB
   icon:https://cdn.rawgit.com/morkysherk/5f3b3e3fbf6cdd7f2c9b73b2e8f2dd6b/raw/60452f1fa9fa44c93bad8a20f0a4c75d8cb60c28/peabCrystal.svg
*/

	//CONVERTER UPGRADES
	
	*movingAssemblyO
		name:Better ratio
		desc:Needs less pea and more nut!<//><.>Multiplies yield of peas and nuts converters by <b>2</b>.
		cost:7500 peanutButter
		passive:multiply yield of pbFactory by 2
		req:1 pbFactory:max
		req:movingAssembly
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*factoredO
		name:Wider nut variety
		desc:More kinds of nuts to convert.<//><.>Multiplies yield of peas and nuts converters by <b>2</b>.
		cost:75000 peanutButter
		passive:multiply yield of pbFactory by 2
		req:10 pbFactories:max
		req:factored
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*factorialO
		name:Green bean converter
		desc:Kinda similar to peas? I guess?<.>Multiplies yield of peas and nuts converters by <b>2</b>.
		cost:750000 peanutButter
		req:25 pbFactories:max
		passive:multiply yield of pbFactory by 2
		req:factorial
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
	*secretIngredientO
		name:Secret ingredient
		desc:This Woman Found The Secret Ingredient To Quick Conversion! Peanut Butter Companies <b>HATE</b> Her! Click <b>HERE</b> To Find Out Her One Simple Trick!<//><.>Multiplies yield of peas and nuts converters by <b>4</b>.<.><i>End of tier 1</i>
		cost:7500000 peanutButter
		req:50 pbFactories:max
		passive:multiply yield of pbFactory by 4
		req:secretIngredient
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
/*
	*bronzePeaNutO
		name:Bronze pea and nut
		cost:1 goldBean
		desc:a feature
		req:bronzePeaNut
	icon:https://cdn.rawgit.com/morkysherk/ca6a3b1468179467b9d400094c71da60/raw/d0ae31a82d265cfe22eb6f6786f2548a88775884/convBronze.svg
*/
	
	//FACTORY UPGRADES
	
	*movingAssemblyAO
		name:Moving assembly line
		desc:Aren't these pretty much the default these days?<//><.>Multiplies yield of peanut butter factories by <b>2</b>.
		cost:112500 peanutButter
		passive:multiply yield of factories by 2
		req:1 factories:max
		req:movingAssembly
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*factoredAO
		name:Factored factories
		desc:In simplest form.<//><.>Multiplies yield of peanut butter factories by <b>2</b>.
		cost:1125000 peanutButter
		passive:multiply yield of factories by 2
		req:10 factories:max
		req:factoredA
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*factorialAO
		name:Factorial factories
		desc:Surprisingly, 200-40*2 is only 5!<//><.>Multiplies yield of peanut butter factories by <b>2</b>.
		cost:11250000 peanutButter
		req:25 factories:max
		req:factorialA
		passive:multiply yield of factories by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*scaleFactorO
		name:Scale factor
		desc:Dilated by a scale factor of 2.<//><.>Multiplies yield of peanut butter factories by <b>4</b>.<.><i>End of tier 1</i>
		cost:112500000 peanutButter
		req:50 factories:max
		req:scaleFactor
		passive:multiply yield of factories by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg

	//REPLICATOR UPGRADES
	
	*triplersO
		name:Triplers
		desc:Get an extra bar of chocolate and jar of peanut butter every time.<//><.>Multiplies yield of replicators by <b>2</b>.
		cost:1687500 chocolate
		cost:1687500 peanutButter
		req:1 replicator:max
		req:triplers
		icon:https://cdn.rawgit.com/morkysherk/c399adb84f6c2b88465731f8ec1353e9/raw/05801ea4697148eb702ca01ff573a6bec4381af5/x3.svg
		passive:multiply yield of replicators by 2
	*quintuplersO
		name:Quintuplers
		desc:Get 3 extra bars of chocolate and jars of peanut butter every time.<//><.>Multiplies yield of replicators by <b>2</b>.
		cost:16875000 chocolate
		cost:16875000 peanutButter
		req:10 replicators:max
		req:quintuplers
		icon:https://cdn.rawgit.com/morkysherk/f0ee659a64b86417081498339daa784e/raw/d61355dcc84be9bbbe53deb20acd657326c28e0a/x5.svg
		passive:multiply yield of replicators by 2
	*nonuplersO
		name:Nonuplers
		desc:Get 7 extra bars of chocolate and jars of peanut butter every time.<//><.>Multiplies yield of replicators by <b>2</b>.
		cost:168750000 chocolate
		cost:168750000 peanutButter
		req:25 replicators:max
		req:nonuplers
		icon:https://cdn.rawgit.com/morkysherk/a9ce3fbbccb4f2cd425c1866a099718a/raw/0b8c26732d0a1f764af3b43bdd886d31472b48e0/x9.svg
		passive:multiply yield of replicators by 2
	*tretrigintuplersO
		name:Tretrigintuplers
		desc:I couldn't quite fit the X in, sorry.<//><.>Multiplies yield of replicators by <b>4</b>.<.><i>End of tier 1</i>
		cost:1687500000 chocolate
		cost:1687500000 peanutButter
		req:50 replicators:max
		req:tretrigintuplers
		icon:https://cdn.rawgit.com/morkysherk/61d92ff0ff3b0faac72c45ae246d5b48/raw/cf73df6ee2f1d2c99b70d5150f20d9f7926a8009/x33.svg
		passive:multiply yield of replicators by 4

	//CORE EXTRACTOR UPGRADES

	*deeperExtractionO
		name:Deeper extraction
		desc:Go deeper into the planet's delicious, gooey core.<.>Multiplies yield of core extractors by <b>2</b>.
		cost:27000000 chocolate
		cost:27000000 peanutButter
		req:1 coreExtractor:max
		req:deeperExtraction
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		passive:multiply yield of coreExtractor by 2
	*coolersO
		name:Coolers
		desc:Make your scorching hot peanut butter and chocolate nice and cool. As a side effect, you may catch them using the latest trendy lingo.<.>Multiplies yield of core extractors by <b>2</b>.
		cost:270000000 chocolate
		cost:270000000 peanutButter
		req:10 coreExtractors:max
		req:coolers
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		passive:multiply yield of coreExtractor by 2
	*fasterTransportO
		name:Faster transportation
		desc:Sure takes a while for things to get from the core to the surface.<.>Multiplies yield of core extractors by <b>2</b>.
		cost:2700000000 chocolate
		cost:2700000000 peanutButter
		req:25 coreExtractors:max
		req:fasterTransportation
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		passive:multiply yield of coreExtractor by 2
	*otherPlanetsO
		name:Other planets
		desc:Extracting from other planets' cores has a much higher output! It's also less damaging to Earth but that's not what matters.<.>Multiplies yield of core extractors by <b>4</b>.<.><i>End of tier 1</i>
		cost:27000000000 chocolate
		cost:27000000000 peanutButter
		req:50 coreExtractors:max
		req:otherPlanets
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/2ce082b468d4fb8335ca2b2585e9612c/raw/b667b66cc0b191e872c9f4ce1792316a03942b51/otherPlanet.svg
		passive:multiply yield of coreExtractor by 4

	//DOWNLOADER UPGRADES

	*quantumPBCO
		name:Quantum peanut butter and chocolate
		desc:It's quantum compatible!<.>Multiplies yield of quantum downloaders by <b>2</b>.
		cost:607500000 chocolate
		cost:607500000 peanutButter
		req:1 qDownloader:max
		passive:multiply yield of qDownloaders by 2
		req:quantumPBC
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*gbWifiO
		name:Gigabit Wi-Fi
		desc:gotta download fast<.>Multiplies yield of quantum downloaders by <b>2</b>.
		cost:6075000000 chocolate
		cost:6075000000 peanutButter
		req:10 qDownloaders:max
		passive:multiply yield of qDownloaders by 2
		req:gbWifi
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*qMechanicO
		name:A quantum mechanic
		desc:Fixes your quantum downloaders when they break.<.>Multiplies yield of quantum downloaders by <b>2</b>.
		cost:60750000000 chocolate
		cost:60750000000 peanutButter
		req:25 qDownloaders:max
		passive:multiply yield of qDownloaders by 2
		req:qMechanic
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg
	*qInternetO
		name:Quantum internet
		desc:At this point, why not just make everything quantum?<.>Multiplies yield of quantum downloaders by <b>4</b>.<.><i>End of tier 1</i>
		cost:607500000000 chocolate
		cost:607500000000 peanutButter
		req:50 qDownloaders:max
		passive:multiply yield of qDownloaders by 4
		req:qInternet
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/c58075d02c2703abab4c8f935be3e56d/raw/25cabcdc4c1028a9dd6fc4eb9bcfd2dc1590007d/qDL.svg

	//MIND READER UPGRADES

	*adsO
		name:Advertisements
		desc:Spread the word!<.>Multiplies yield of mind readers by <b>2</b>.
		passive:multiply yield of mindReaders by 2
		req:ads
		cost:13668750000 chocolate
		cost:13668750000 peanutButter
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg
	*subliminalO
		name:Subliminal messaging
		desc:<.>Multiplies yield of mind readers by <b>2</b>.
		passive:multiply yield of mindReaders by 2
		req:subliminal
		cost:136687500000 chocolate
		cost:136687500000 peanutButter
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg
	*hallucinogensO
		name:Hallucinogens
		desc:if I wasn't eating chocolate that whole time... what was I eating?<.>Multiplies yield of mind readers by <b>2</b>.
		passive:multiply yield of mindReaders by 2
		req:hallucinogens
		cost:1366875000000 chocolate
		cost:1366875000000 peanutButter
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg
	*mindControlO
		name:Mind control
		desc:Put on your tinfoil hats!<.>Multiplies yield of mind readers by <b>4</b>.
		passive:multiply yield of mindReaders by 4
		req:mindControl
		cost:13668750000000 chocolate
		cost:13668750000000 peanutButter
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/fafed1a756ac5581383b8ccb306b64c1/raw/1074b726d041607da8747e6d65ff39b4027308db/thot.svg

	//CUPPER UPGRADES
		
	*nimbleFingersO
		name:Nimble fingers
		desc:Trim off the fat and get some muscle memory.<//><.>Multiplies yield of peanut butter cuppers by <b>2</b>.
		cost:1000 chocolate
		cost:1000 peanutButter
		cost:250 peanutCups
		req:1 peanutCupper:max
		passive:multiply yield of peanutCupper by 2
		req:nimbleFingers
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*cupManufacturersO
		name:Cup manufacturers
		desc:These guys have a lot of experience making cups. That should translate well into making peanut butter cups, right?<//><.>Multiplies yield of peanut butter cuppers by <b>2</b>.
		cost:10000 chocolate
		cost:10000 peanutButter
		cost:2500 peanutCups
		req:10 peanutCuppers:max
		passive:multiply yield of peanutCupper by 2
		req:cupManufacturers
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*chefsO
		name:Chefs
		desc:Cooks up some fresh peanut butter cups.<//><.>Multiplies yield of peanut butter cuppers by <b>2</b>.<q>Are the peanut butter cups fresh or frozen?</q>
		cost:100000 chocolate
		cost:100000 peanutButter
		cost:25000 peanutCups
		req:25 peanutCuppers:max
		req:chefs
		passive:multiply yield of peanutCupper by 2
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*magesO
		desc:Casts spells on your peanut butter and chocolate to form peanut butter cups.<.>Multiplies yield of peanut butter cuppers by <b>4</b>.<.><i>End of tier 1</i>
		name:Mages
		cost:1000000 chocolate
		cost:1000000 peanutButter
		cost:250000 peanutCups
		req:50 peanutCuppers:max
		req:mages
		passive:multiply yield of peanutCupper by 4
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
/*
	*awwwawdwdwd awda d ddddddOOOOOOOOOOO
		name:Seemeeks cube
		desc:If you don't get this, you probably don't have a solid enough grasp of theoretical physics.<.>Multiplies yield of peanut butter cuppers by <b>4</b>.<//><q>"CAN DO!"</q>
		icon:numbers[5,0] https://imgur.com/XyuOrLu.png
		req:51 peanutCuppers:max
		cost:1000000 chocolate
		cost:1000000 peanutButter
		cost:250000 peanutCups
		passive:multiply yield of peanutCupper by 3
*/

	//MACHINE UPGRADES
		
	*wcO
		name:WC-50
		desc:Makes things go.<//><.>Multiplies yield of cup machines by <b>2</b>.
		cost:15000 peanutCups
		req:1 cupMachine:max
		req:wc
		passive:multiply yield of cupMachine by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*cheaperMetalO
		name:Cheaper Metal
		desc:Refineries, factories, and machines are <b>5%</b> cheaper.
		cost:75000 peanutCups
		passive:multiply cost of cupMachine by 0.95
		passive:multiply cost of factory by 0.95
		passive:multiply cost of chocoFarm by 0.95
		req:5 cupMachines:max
		req:10 factories:max
		req:10 chocoFarms:max
		req:cheaperMetal
		icon:https://cdn.rawgit.com/morkysherk/82a70ae5ca004b88d52db0a8d383bc16/raw/84927ce67cde4be2717272266a06565771220240/dolla.svg
	*lighterMachineryO
		name:Lighter Machinery
		cost:150000 peanutCups
		desc:Try our new weight loss programs for machines!<.>Multiplies yield of cup machines by <b>2</b>.
		req:10 cupMachines:max
		passive:multiply yield of cupMachines by 2
		req:lighterMachinery
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*hqCogsO
		name:High quality cogs
		cost:1500000 peanutCups
		desc:For smoother rotation.<.>Multiplies yield of cup machines by <b>2</b>.
		passive:multiply yield of cupMachines by 2
		req:hqCogs
		req:25 cupMachines:max
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
	*microMachinesO
		name:Micro-machines
		cost:15000000 peanutCups
		desc:These can move anything anywhere, with ease. If you can think it, they can do it. The only limit is your imagination.<.>Multiplies yield of cup machines by <b>4</b>.<.><i>End of tier 1</i>
		req:microMachines
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
		req:50 cupMachines:max
		passive:multiply yield of cupMachines by 2

	//PRINTER UPGRADES

	*fasterPrintingO
		name:Faster printers
		desc:The printhead can move faster.<//><.>Multiplies yield of 3D printers by <b>2</b>.
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:175000 peanutCups
		passive:multiply yield of printers by 2
		req:fasterPrinting
		req:1 printer:max
	*optimizedModelsO
		name:Optimized models
		desc:These more efficient models will cut printing time in half.<//><.>Multiplies yield of 3D printers by <b>2</b>.
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:1750000 peanutCups
		passive:multiply yield of printers by 2
		req:optimizedModels
		req:10 printers:max
	*biggerFeederO
		name:Bigger material feeder
		desc:With this, you won't need to refill your printer as often.<//><.>Multiplies yield of 3D printers by <b>2</b>.
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:17500000 peanutCups
		passive:multiply yield of printers by 2
		req:biggerFeeder
		req:25 printers:max
	*biggerPrintheadO
		name:Bigger printhead
		desc:Your printers can squirt out more stuff at once.<//><.>Multiplies yield of 3D printers by <b>4</b>.<.><i>End of tier 1</i>
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		cost:175000000 peanutCups
		passive:multiply yield of printers by 2
		req:biggerPrinthead
		req:50 printers:max

	//PUKER UPGRADES
	
	*largeStomachO
		name:Large stomach
		desc:Pukers can hold more peanut butter and chocolate in their stomach.<//><.>Multiplies yield of cup pukers by <b>2</b>.
		cost:2000000 peanutCups
		req:1 cupVomiter:max
		passive:multiply yield of cupVomiter by 2
		req:largeStomach
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
	*fastDigestionO
		name:Fast digestion
		desc:Pukers digest faster.<//><.>Multiplies yield of cup pukers by <b>2</b>.
		cost:20000000 peanutCups
		req:10 cupVomiters:max
		req:fastDigestion
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		passive:multiply yield of cupVomiter by 2
	*defecationO
		name:Defecation
		desc:Even more gross. Still safe, though. Probably.<//><.>Multiplies yield of cup pukers by <b>2</b>.
		cost:200000000 peanutCups
		req:25 cupVomiters:max
		req:defecation
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		passive:multiply yield of cupVomiter by 2
	*inhaleO
		name:Inhale ability
		desc:Sucks in the peanut butter and chocolate.<.>Multiplies yield of cup pukers by <b>4</b>.<.><i>End of tier 1</i>
		cost:2000000000 peanutCups
		req:50 cupVomiters:max
		req:inhale
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		passive:multiply yield of cupVomiter by 4

	//REARRANGER UPGRADES

	*breakdownO
		name:Molecular breakdown
		desc:Breaking down molecules makes them easier to rearrange.<//><.>Multiplies yield of molecular rearrangers by <b>2</b>.
		cost:25000000 peanutCups
		req:1 rearranger:max
		passive:multiply yield of rearranger by 2
		req:breakdown
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*noclipO
		name:I accidentally left this name as a placeholder for a long time so I'll just leave this here as a monument to my forgetfulness
		desc:At least I won't have to think of a name now.<//><.>Multiplies yield of molecular rearrangers by <b>2</b>.
		cost:250000000 peanutCups
		req:10 rearrangers:max
		passive:multiply yield of rearranger by 2
		req:noclip
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*chocolateMoleculesO
		name:Chocolate molecules
		desc:Chocolate can now be made with a single type of molecule.<//><.>Multiplies yield of molecular rearrangers by <b>2</b>.
		cost:2500000000 peanutCups
		req:25 rearrangers:max
		passive:multiply yield of rearranger by 2
		req:chocolateMolecules
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
	*quantumTunnelingO
		name:Quantum tunneling
		desc:Molecules go straight through each other.<.>Multiplies yield of molecular rearrangers by <b>4</b>.<.><i>End of tier 1</i>
		cost:25000000000 peanutCups
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
		req:50 rearrangers:max
		req:quantumTunneling
		passive:multiply yield of rearranger by 4

	//SHIP UPGRADES
	
	*betterBargainingO
		name:Better bargaining
		desc:Best I can do is 20 peanut butter cups.<//><.>Multiplies yield of trade spaceships by <b>2</b>.
		cost:300000000 peanutCups
		req:1 rocketShip:max
		passive:multiply yield of rocketShip by 2
		req:betterBargaining
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*hotDealsO
		name:Hot deals
		desc:50% off!<//><.>Multiplies yield of trade spaceships by <b>2</b>.
		cost:3000000000 peanutCups
		req:10 rocketShips:max
		passive:multiply yield of rocketShip by 2
		req:hotDeals
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*memberCardO
		name:Membership card
		desc:Get rewarded for your loyalty.<//><.>Multiplies yield of trade spaceships by <b>2</b>.
		cost:30000000000 peanutCups
		req:25 rocketShips:max
		passive:multiply yield of rocketShip by 2
		req:memberCard
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
	*hyperDriveO
		name:Hyperdrive
		desc:The key to fast, efficient space travel.<//><.>Multiplies yield of trade spaceships by <b>4</b>.<.><i>End of tier 1</i>
		cost:300000000000 peanutCups
		passive:multiply yield of rocketShip by 4
		req:50 rocketShips:max
		req:hyperDrive
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
/*
	*scamsO
		name:Scams
		desc:<.>Trade spaceships use <b>20%</b> less chocolate and peanut butter.
*/

	//PORTAL UPGRADES

	*fasterPortalsO
		name:Faster portals
		desc:Skip the cutscene for going through a portal.<//><.>Multiplies yield of portals by <b>2</b>.
		cost:3250000000 peanutCups
		req:1 cupPortal:max
		passive:multiply yield of cupPortal by 2
		req:fasterPortals
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*betterDimensionO
		name:Better dimension
		desc:Turns out whatever was in that other dimension was slacking off.<//><.>Multiplies yield of portals by <b>2</b>.
		cost:32500000000 peanutCups
		req:10 cupPortals:max
		passive:multiply yield of cupPortal by 2
		req:betterDimension
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*theCakeO
		name:The cake
		desc:It's a lie. This is the pinnacle of low-hanging fruit.<.>Multiplies yield of portals by <b>2</b>.
		cost:325000000000 peanutCups
		req:25 cupPortals:max
		passive:multiply yield of cupPortal by 2
		req:theCake
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*fourthDimensionO
		name:Fourth dimension
		desc:The thrilling sequel to the third dimension.<.>Multiplies yield of portals by <b>4</b>.<.><i>End of tier 1</i>
		cost:3250000000000 peanutCups
		req:50 cupPortals:max
		passive:multiply yield of cupPortal by 4
		req:fourthDimension
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*multiDimensionalO
		name:Multidimensional portals
		desc:Send peanut butter and chocolate to multiple dimensions at the same time.<.>Multiplies yield of portals by <b>3</b>.
		cost:32500000000000 peanutCups
		req:75 cupPortals:max
		passive:multiply yield of cupPortal by 3
		req:multiDimensional
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*portalGunsO
		name:Portal guns
		desc:More convenient, as long as you can find a matte white surface nearby.<.>Multiplies yield of portals by <b>3</b>.
		cost:325000000000000 peanutCups
		req:100 cupPortals:max
		passive:multiply yield of cupPortal by 3
		req:portalGuns
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg

	//MYSTERY BOX UPGRADES
	
	*biggerBoxesO
		name:Bigger boxes
		desc:We're gonna need a bigger box?<//><.>Multiplies yield of mystery boxes by <b>2</b>.
		cost:35000000000 peanutCups
		req:1 mysteryBox:max
		passive:multiply yield of mysteryBox by 2
		req:biggerBoxes
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*addedMysteryO
		name:Added mystery
		desc:The suspense is killing me.<//><.>Multiplies yield of mystery boxes by <b>2</b>.
		cost:350000000000 peanutCups
		req:10 mysteryBoxes:max
		passive:multiply yield of mysteryBox by 2
		req:addedMystery
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*schrodingersCatO
		name:Schrodinger's cat
		desc:Just hangs out in the mystery box with your peanut butter and chocolate.<.>Multiplies yield of mystery boxes by <b>2</b>.
		cost:3500000000000 peanutCups
		req:25 mysteryBoxes:max
		passive:multiply yield of mysteryBox by 2
		req:schrodingersCat
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*boxSquaredO
		name:Mystery box²
		desc:Send mystery boxes full of peanut butter cups through other mystery boxes.<.>Multiplies yield of mystery boxes by <b>4</b>.<.><i>End of tier 1</i>
		cost:35000000000000 peanutCups
		req:boxSquared
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg

	//SUBATOMIC UPGRADES

	*bingBongO
		name:Bing bong theory
		desc:Bazoomba<//><.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>2</b>.
		cost:400000000000 peanutCups
		req:bingBong
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*ropeTheoryO
		name:Rope theory
		desc:Because strings are far too small.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>2</b>.
		cost:4000000000000 peanutCups
		req:ropeTheory
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*scientificScienceO
		name:Scientific science
		desc:It just wasn't quite scientific enough before.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>2</b>.
		cost:40000000000000 peanutCups
		req:scientificScience
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*subsubAtomicO
		name:Subsubatomic particles
		desc:What <i>really</i> makes up the universe.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>4</b>.<.><i>End of tier 1</i>
		cost:400000000000000 peanutCups
		req:subsubAtomic
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*superConvapitatorO
		name:Supercharged convapitators
		desc:Although the subatomic moleculization is an important part of the convapitation process, it all falls apart if the convapitators themselves can't convapitate well enough.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>3</b>.
		cost:4000000000000000 peanutCups
		req:superConvapitator
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*molecularSubitizerO
		name:Molecular subatomicizers
		desc:Pull the ol' switcheroo.<.>Multiplies yield of subatomic moleculizers of the Greek bose-stein convapitators by <b>3</b>.
		cost:40000000000000000 peanutCups
		req:molecularSubitizer
		icon:numbers[6,1] https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg

	//EXTRACTOR UPGRADES
	
	*suckierHolesO
		name:Suckier holes
		desc:uhh<.>Multiplies yield of black hole extractors by <b>2</b>.
		cost:6789012345670 peanutCups
		req:1 bhExtractor:max
		req:suckierHoles
		passive:multiply yield of bhExtractor by 2
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*eventfulHorizonsO
		name:More eventful horizons
		desc:Action-packed!<.>Multiplies yield of black hole extractors by <b>2</b>.
		cost:67890123456701 peanutCups
		req:10 bhExtractors:max
		passive:multiply yield of bhExtractor by 2
		req:eventfulHorizons
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*antiSpaghettiO
		name:Spaghettification prevention
		desc:Do I make a "hope she made lotsa spaghetti" joke or a "somebody toucha my spaghet" joke? Or will both of these jokes eventually be long forgotten and make my game dated?<.>Multiplies yield of black hole extractors by <b>2</b>.
		cost:678901234567012 peanutCups
		req:25 bhExtractors:max
		passive:multiply yield of bhExtractor by 2
		req:antiSpaghetti
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*galacticCoresO
		name:Galactic cores
		desc:As some of the most massive black holes in the universe, these can have entire galaxies orbiting them. They should do the trick.<.>Multiplies yield of black hole extractors by <b>4</b>.<.><i>End of tier 1</i>
		cost:6789012345670123 peanutCups
		req:50 bhExtractor:max
		passive:multiply yield of bhExtractor by 4
		req:galacticCores
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg
	*compactDisksO
		name:Compact accretion disks
		desc:Way better than the floppy ones.<.>Multiplies yield of black hole extractors by <b>3</b>.
		req:compactDisks
		icon:numbers[5,1] https://cdn.rawgit.com/morkysherk/8e127a80d2cf19f09bd1a93f559a87e3/raw/23e9e9f5b149d166fdd816da8c1be6d732e96131/bHole.svg

	//ANOMALY UPGRADES

	*longRangeO
		name:Long-range anomalies
		desc:Convert things from <i>coast to coast</i>.<.>Multiplies yield of space-time anomalies by <b>2</b>.
		cost:115000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:longRange
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*blindSpotsO
		name:Blind spots
		desc:Wow, you're so insensitive (to light)<.>Multiplies yield of space-time anomalies by <b>2</b>.
		cost:1150000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:blindSpots
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*loweredFOVO
		name:Lowered FOV
		desc:I'm sure no one will notice.<.>Multiplies yield of space-time anomalies by <b>2</b>.
		cost:11500000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:loweredFOV
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg
	*instantConversionO
		name:Instant conversion
		desc:The mere blink of an eye could get your peanut butter and chocolate converted!<.>Multiplies yield of space-time anomalies by <b>4</b>.<.><i>End of tier 1</i>
		cost:115000000000000000 peanutCups
		passive:multiply yield of anomalies by 2
		req:instantConversion
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/910b05f5526ceea98d0365baa45df953/raw/c95455608f83b26955803cd5352cc3636b88bc90/anomaly.svg



Achievements
	*TEMPLATE
		no text
		class:smallThing
		on click:
			if (clickAnimation=1)
				anim icon wobble2
				anim wobble2
			end
			if (clickAnimation=2)
				anim icon bounceOnce
				anim bounceOnce
			end
			if (clickAnimation=3)
				anim icon plop
				anim plop
			end
			if (clickAnimation=4)
				anim icon wiggling2
				anim wiggling
			end
			if (clickAnimation=5)
				anim icon wobbleSlow
				anim wobbleSlow
			end
		end
		tag:achievement
		on earn:yield 1 achievPoint
		no text
	*itBegins
		name:It begins
		desc:Who would win? Your free time VS. one <i>i d l e  b o i</i><//><.>Make peanut butter and chocolate.
		req:1 peanutButter
		req:1 chocolate
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
	*upandCup
		name:Get up and cup
		desc:Make your first peanut butter cup.
		req:1 peanutCup:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue25 smallThing
	*eatemUp
		name:Eat em up
		desc:The flavor you savor.<//><.>Make <b>1,000</b> peanut butter cups.
		req:1000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue50 smallThing
	*pbchocolateFlavor
		name:Peanut butter chocolate flavor
		desc:What you wake up to.<//><.>Make <b>100,000</b> peanut butter cups.
		req:100000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue75 smallThing
	*peanutbuttercupHead
		name:Peanut butter cuphead
		desc:The peanut butter dark souls of achievements!<//><.>Make <b>1,000,000</b> peanut butter cups.
		req:1000000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue100 smallThing
	*massProduce
		name:Mass produce
		desc:Like the vegetables?<//><.>Make <b>100,000,000</b> peanut butter cups.
		req:100000000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue125 smallThing
	*aLot
		name:A lot
		desc:Exactly 1 lot.<//><.>Make <b>1 billion</b> peanut butter cups.
		req:1000000000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue150 smallThing
	*plenty
		name:Plenty
		desc:Yep.<//><.>Make <b>100 billion</b> peanut butter cups.
		req:100000000000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue175 smallThing
	*lifeSupply
		name:Lifetime supply
		desc:Maybe even more.<//><.>Make <b>1 trillion</b> peanut butter cups.
		req:1000000000000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue200 smallThing
	*Surplus
		name:Surplus
		desc:Definitely more than you need.<//><.>Make <b>100 trillion</b> peanut butter cups.
		req:100000000000000 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue225 smallThing
	*notEnough
		name:Yet still not enough
		desc:Apparently.<.>Make <b>1 quadrillion</b> peanut butter cups.
		req:1e15 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue250 smallThing
	*pbInTheChocolate
		name:You put the PB in the chocolate
		desc:And eat 'em both together.<.>Make <b>100 quadrillion</b> peanut butter cups.
		req:1e17 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue275 smallThing
	*loadsofCups
		name:Lods of echocolat
		desc:what's that spell?<.>Make <b>1 quintillion</b> peanut butter cups.
		req:1e18 peanutCups:earned
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		class:hue300 smallThing
	*hired
		name:You're Hired
		desc:Hire all 3 types of workers.
		req:1 peanutButterer
		req:1 chocolateWorker
		req:1 peanutCupper
		icon:https://cdn.rawgit.com/morkysherk/6df06c87ebef0a29f7bbe018afc1737c/raw/b74565c9a4d04514a62b105c9df08c67e8dce7da/all3.svg
	*hardlyWorking
		name:Hardly working
		desc:Hire <b>10</b> chocolate workers.
		req:10 chocolateWorker
		icon:https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
		class:hue25 smallThing
	*workingHard
		name:Working hard
		desc:Hire <b>25</b> chocolate workers.	
		req:25 chocolateWorkers
		icon:https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
		class:hue50 smallThing
	*employer
		name:Employer
		desc:Hire <b>50</b> chocolate workers.
		req:50 chocolateWorkers
		icon:https://cdn.rawgit.com/morkysherk/f5be1f499ee6312e9810b9371b4da3af/raw/40da9c994decfa5c6d956e061ed157897ec88ac6/choco.svg
		class:hue75 smallThing
	*treeFarmer
		name:Homegrown
		desc:Have <b>1</b> chocolate farm.
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:1 refinery
	*homegrown
		name:Tree farmer
		desc:Have <b>10</b> chocolate farms.
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:10 refinery
		class:hue25 smallThing
	*acres
		name:Acres upon acres
		desc:Have <b>25</b> chocolate farms.
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:25 refinery
		class:hue50 smallThing
	*hectares
		name:Hectares upon hectares
		desc:Have <b>50</b> chocolate farms.
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:50 refinery
		class:hue75 smallThing
	*farmsim
		name:Farming simulator
		desc:I'm not using it as proper noun so it's not copyright infringement! Brilliant!<.>Have <b>75</b> chocolate farms.
		icon:https://cdn.rawgit.com/morkysherk/f5c64664f71b3f9e2f4b91de4cc1bfdb/raw/4752f2af732f2debce18ead8a31b651ecc010d69/farm.svg
		req:75 refinery
		class:hue100 smallThing
	*refinedTaste
		name:Refined taste
		desc:Have <b>1</b> chocolate refinery.
	  icon:https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:1 chocoFarm
	*groundBeans
		name:Ground beans
		desc:Also known as bean mince or minced beans.<.>Have <b>10</b> chocolate refineries.
	  icon:https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:10 chocoFarms
		class:hue25 smallThing
	*dailyGrind
		name:The daily grind
		desc:Have <b>25</b> chocolate refineries.
	  icon:https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:25 chocoFarms
		class:hue50 smallThing
	*captainConch
		name:Captain Conch
		desc:<i>Conchatize me</i><.>Have <b>50</b> chocolate refineries.<.>someone's gotta know what conching is, right?
	  icon:https://cdn.rawgit.com/morkysherk/751cab83d87772656cde4305358c0b6e/raw/fccdbb77f45b4bafec7bc5cd08ad01b44f42c1ac/refinery.svg
		req:50 chocoFarms
		class:hue75 smallThing
	*peanutButtered
		name:Peanut buttered
		desc:Hire <b>10</b> peanut butterers.
	   icon:https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
		req:10 peanutButterers
		class:hue25 smallThing
	*creamy
		name:Creamy
		desc:Mmm-mmm... creamy.<.>Hire <b>25</b> peanut butterers.<.>this icon is O g r e  C o l o r e d (if you have CSS filters on)
	   icon:https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
		req:25 peanutButterers
		class:hue50 smallThing
	*crunchy
		name:Crunchy
		desc:Delicious crunch flavor.<.>Hire <b>50</b> peanut butterers.
	   icon:https://cdn.rawgit.com/morkysherk/d2cfc2c31d80bf249fda9fb7e28b130c/raw/84bfdea38a2717c936c480edf394fd66806825a7/peabnut.svg
		req:50 peanutButterers
		class:hue75 smallThing
	*converted
		name:Converted to converting
		desc:Have <b>1</b> peas and nuts converter.
	  icon:https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
		req:1 pbFactory
	*theyreBack
		name:PEAS ARE BACK, AND THIS TIME THEY'VE BROUGHT NUTS
		desc:FOR THE ULTIMATE KART RACING ADVENTURE<.>Have <b>10</b> peas and nuts converters.
	  icon:https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
		req:10 pnConverters
		class:hue25 smallThing
	*peaSandnuts
		name:Pea sand nuts
		desc:Don't misplace the space<.>Have <b>25</b> peas and nuts converters.
	  icon:https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
		req:25 pnConverters
		class:hue50 smallThing
	*peaceandNuts
		name:Peace and nuts
		desc:Your peas and nuts have brought peace among worlds.<.>Have <b>50</b> peas and nuts converters.
	  icon:https://cdn.rawgit.com/morkysherk/2b40b85379aadfa6915979f2dfade403/raw/408447da2335b0b82aa4fc3366cf8acb277e01da/peasNuts.svg
		req:50 pnConverters
		class:hue75 smallThing
	*manufacturer
		name:Manufacturer
		desc:Have <b>1</b> peanut butter factory.
		req:1 factory
	 icon:https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
	*producer
		name:Producer
		desc:Have <b>10</b> peanut butter factories.
		req:10 factory
	 icon:https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
		class:hue25 smallThing
	*GCF
		name:Greatest common factor
		desc:Yet this joke is the lowest common denominator.<.>Have <b>25</b> peanut butter factories.
		req:25 factory
	 icon:https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
		class:hue50 smallThing
	*FOIL
		name:Using FOIL
		desc:Yep, these are all gonna be math-related. Woohoo.<.>Have <b>50</b> peanut butter factories.
		req:50 factory
	 icon:https://cdn.rawgit.com/morkysherk/645e7182d29efc2a1078f0504e2a4e6f/raw/332ea27669218dfde408f8de93b6c006036523e5/pbFactory.svg
		class:hue75 smallThing
	*easytoReplicate
		name:Easy to replicate
		desc:Helpful when finding and fixing bugs.<.>Have <b>1</b> replicator.
		req:1 replicator
	icon:https://cdn.rawgit.com/morkysherk/52ab77aa07ae52a02994ad81c32e93f3/raw/3f64bc9762ac1154994d513193bf03f68aa41ba6/replicator.svg
	*replicants
		name:Replicants
		desc:Nearly identical to peanut butter cups, but with superior tastiness, chocolatiness, and healthiness.<.>Have <b>10</b> replicators.
		req:10 replicators
	icon:https://cdn.rawgit.com/morkysherk/52ab77aa07ae52a02994ad81c32e93f3/raw/3f64bc9762ac1154994d513193bf03f68aa41ba6/replicator.svg
		class:hue25 smallThing
	*cloneWars
		name:Clone wars
		desc:You might have heard of these a little while ago in a neighboring galaxy.<.>Have <b>25</b> replicators.
	icon:https://cdn.rawgit.com/morkysherk/52ab77aa07ae52a02994ad81c32e93f3/raw/3f64bc9762ac1154994d513193bf03f68aa41ba6/replicator.svg
		class:hue50 smallThing
		req:25 replicators
	*doubleDouble
		name:Double-double
		desc:It's a real shame if you don't live anywhere with an In-N-Out. Unless you have A&W. I like that too.<.>Have <b>50</b> replicators.
	icon:https://cdn.rawgit.com/morkysherk/52ab77aa07ae52a02994ad81c32e93f3/raw/3f64bc9762ac1154994d513193bf03f68aa41ba6/replicator.svg
		req:50 replicators
		class:hue75 smallThing
	*pbcExtract
		name:Peanut butter and chocolate extract
		desc:Have <b>1</b> core extractor.
		req:1 coreExtractor
		icon:https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
	*deepDish
		name:Deep dish
		desc:Straight from Chicago.<.>Have <b>10</b> core extractors.
		req:10 coreExtractors
		icon:https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		class:hue25 smallThing
	*superHeated
		name:Superheated
		desc:Have <b>25</b> core extractors.
		req:25 coreExtractors
		icon:https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		class:hue50 smallThing
	*commonCore
		name:Common core
		desc:<.>Have <b>50</b> core extractors.
		req:50 coreExtractors
		icon:https://cdn.rawgit.com/morkysherk/4b5a464729fd860dab870581339e6d65/raw/b1cba0029067fc4a2663b4a588ef99ef620a6253/planet.svg
		class:hue75 smallThing
	*peanutbutterCupped
		name:Peanut butter cupped
		desc:Hire <b>10</b> peanut butter cuppers.
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		req:10 peanutCuppers
		class:hue25 smallThing
	*cuppitize
		name:Peanut butter cuppitized
		desc:Hire <b>25</b> peanut butter cuppers.
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		req:25 peanutCuppers
		class:hue50 smallThing
	*cuppinated
		name:Peanut butter cuppinated
		desc:-inator-inator-inator<.>Hire <b>50</b> peanut butter cuppers.
		icon:https://cdn.rawgit.com/morkysherk/4ec45beafbbc4ef0773114bae71eb989/raw/83d1753129e14318a3bdcce2a7e58c698326e1d6/reese.svg
		req:50 peanutCuppers
		class:hue75 smallThing
	*automated
		name:Automated
		desc:Have <b>1</b> peanut butter cup machine.
	   icon:https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
		req:1 cupMachine
	*automagical
		name:Automagical
		desc:It's magic!<.>Have <b>10</b> peanut butter cup machines.
	   icon:https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
		req:10 cupMachines
		class:sepiahue25 smallThing
	*burningQuestion
		name:If a bakery is a place where baked goods are made, is a machinery a place where machines are made?
		desc:Top 10 Questions Scientists Still Can't Answer<.>Have <b>25</b> peanut butter cup machines.
	   icon:https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
		req:25 cupMachines
		class:sepiahue50 smallThing
	*cognitive
		name:Cog-nitive
		desc:Hopefully not dissonance.<.>Have <b>50</b> peanut butter cup machines.
	   icon:https://cdn.rawgit.com/morkysherk/fa9d668a4443a5a08de1f548c888c1f6/raw/725c86ebc029f2761d152e8283a8959e3fef0d09/machine.svg
		req:50 cupMachines
		class:sepiahue75 smallThing
	*futureisNow
		name:The future is now
		desc:Have <b>1</b> 3D printer.
	   icon:https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		req:1 printer
	*futurewasyesterday
		name:The future was yesterday
		desc:Well that came and went pretty quickly.<.>Have <b>10</b> 3D printers.
	   icon:https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		req:10 printers
		class:hue25 smallThing
	*printShop
		name:Print shop
		desc:Have <b>25</b> 3D printers.
	   icon:https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		req:25 printers
		class:hue50 smallThing
	*inPrint
		name:In print
		desc:Better not be in cursive!<.>Have <b>50</b> 3D printers.
	   icon:https://cdn.rawgit.com/morkysherk/6fe1c1df5f6a5e5d28be14440c714308/raw/d4c83c3f03a2480fece3d8b629cd06c3c27d97f6/printer.svg
		req:50 printers
		class:hue75 smallThing
	*appetizing
		name:Appetizing
		desc:Have <b>1</b> puker.
		icon:https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		req:1 cupVomiter
	*cupatemesis
		name:Cupatemesis
		desc:<.>Have <b>10</b> pukers.
		icon:https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		req:10 cupVomiters
		class:hue25 smallThing
	*vomitAlready
		name:Vomit on his sweater already
		desc:Mom's cup-etti? I dunno<.>Have <b>25</b> pukers.
		icon:https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		req:25 cupVomiters
		class:hue50 smallThing
	*tooMuchToStomach
		name:Too much to stomach
		desc:Have <b>50</b> pukers.
		icon:https://cdn.rawgit.com/morkysherk/b322f0eb84f6c22b3620858e4a7ec1cc/raw/86c4c401fade1d40735f554162be3200ae110709/puker.svg
		req:50 cupVomiters
		class:hue75 smallThing
	*makingArrangements
		name:Making arrangements
		desc:Have <b>1</b> molecular rearranger.
	  icon:https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
		req:1 rearranger
	*reorganization
		name:Molecular reorganization
		desc:blah blah organization is important!!!<.>Have <b>10</b> molecular rearrangers.
	  icon:https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
		req:10 rearrangers
		class:hue25 smallThing
	*reschedule
		name:Rescheduling
		desc:Because those arrangements didn't work out.<.>Have <b>25</b> molecular rearrangers.
	  icon:https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
		req:25 rearrangers
		class:hue50 smallThing
	*molecularLevel
		name:The Molecular Level
		desc:Have <b>50</b> molecular rearrangers
	  icon:https://cdn.rawgit.com/morkysherk/b0318d383513d95521499e37d5fdfc78/raw/4e3edba050f2068770b1bf16bc1462e261612036/molecule.svg
		req:50 rearrangers
		class:hue50 smallThing
	*cupsinSpace
		name:T minus 10
		desc:Have <b>1</b> trade spaceships.
		icon:https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
		req:1 rocketShip
	*blastOff
		name:Blast off
		desc:Have <b>10</b> trade spaceships.
		icon:https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
		req:10 rocketShips
		class:hue25 smallThing
	*inSpace
		name:Cups in Space
		desc:Have <b>25</b> trade spaceships.
		icon:https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
		req:25 rocketShips
		class:hue50 smallThing
	*tradeRoute
		name:Trade routes established
		desc:<.>Have <b>50</b> trade spaceships.
		icon:https://cdn.rawgit.com/morkysherk/b7d3ae243a102a9b39637190dac20041/raw/4cf30a075e035f8914848479af0faf5f51474f2a/rocket.svg
		req:50 rocketShips
		class:hue75 smallThing
/*
	*masterOfTrade
		name:Master of the trade
*/
	*interDimensional
		name:Interdimensional
		desc:Have <b>1</b> portal.
		req:1 cupPortal
		icon:https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
	*perpendicular
		name:A perpendicular universe
		desc:What's so great about all those parallel ones anyway?<.>Have <b>10</b> portals.
		req:10 cupPortals
		icon:https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
		class:hue25 smallThing
	*worldsCollide
		name:When worlds collide
		desc:Have <b>25<b> portals.
		req:25 cupPortals
		icon:https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
		class:hue50 smallThing
	*ARG
		name:Alternate reality game
		desc:I really don't understand this name.<.>Have <b>50</b> portals.
		req:50 cupPortals
		icon:https://cdn.rawgit.com/morkysherk/90fd792df35169cb0cc96ae35163fdc2/raw/a309035a47d81b016b299eaa50369a83c4f4f8d7/adwadw.svg
		class:hue75 smallThing
	*mysterious
		name:Mysterious
		desc:Have <b>1</b> mystery box.
		req:1 mysteryBox
	   icon:https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
	*whatsInTheBox
		name:What's in the box?
		desc:It's... a bad joke!<.>Have <b>10</b> mystery boxes.
		req:10 mysteryBox
	   icon:https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
		class:sepiahue25 smallThing
	*interrogative
		name:Interrogative
		desc:Make sure it's not derogative.<.>Have <b>25</b> mystery boxes.
		req:25 mysteryBox
	   icon:https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
		class:sepiahue50 smallThing
	*wot
		name:?̣̣̭͓̞̻̳̋͆͂̐ͥ͠ͅ?̧̼̘̻̯̩̲͓̖̔͑̿͊̄ͪ̚?̵̻͈̝̦̱̓̋͊?̶̦̪̉̒̏̀͟͝?̘̱͇͉̯͕̞͆ͫ͘?͈̤̳̍͊ͥ͊ͫ?͈̖͈͔͛̐ͨ͆ͮͣ͞͠?͈̣̖̭͈̩͌?̬̰̺̰̲̃̀ͥͤͧ̇̈́?̨̯̘ͩ̓̎ͩͧ͂͆ͅ
		desc:k͜͏j̵͝͡a̡͝w̧̢̕hk̨j͜d̀͞h̢͜͡k̸ j͞h̵́k҉͟͞h͘la̷͠j̡wh͞҉l̸͢jl͡j̶͘áh̵͏͘l͡͡wj ͏͢͞h͝҉̡l̴̕͘ ͠ḑ̵j̕͞h̸͢͠l͏́j̕á̡h̶<.>H̛ávé <b>50</b> mýst͠e̴ry ̶b̵o̴xe̡s̶.
		req:50 mysteryBox
	   icon:https://cdn.rawgit.com/morkysherk/fe8c7c6f3572ec452963b6d4cdafab7b/raw/577232bee7a39636f5cc7e5c57ea022b55bc6b54/mystery.svg
		class:sepiahue75 smallThing
	*sciencingBegins
		name:The sciencing begins
		desc:Have <b>1</b> subatomic moleculizer of the Greek bose-stein convapitators.
		req:1 subAtomic
		icon:https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
	*particules
		name:Partícules
		desc:The lesser-known brother of Hercules?<.>Have <b>10</b> subatomic moleculizers of the Greek bose-stein convapitators.
		req:10 subAtomic
		icon:https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
		class:hue25 smallThing
	*participles
		name:Participles
		desc:They tend to dangle.<.>Have <b>25</b> subatomic moleculizers of the Greek bose-stein convapitators.
		req:25 subAtomic
		icon:https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
		class:hue50 smallThing
	*negativeKelvin
		name:-1 Kelvin
		desc:A tad brisk.<.>Have <b>50</b> subatomic moleculizers of the Greek bose-stein convapitators.
		req:50 subAtomic
		icon:https://cdn.rawgit.com/morkysherk/317a8336e3d9752b507ea9b5d45575c0/raw/1a107f416d77fa6bd2e60655552f8d7887f96a6c/atom.svg
		class:hue75 smallThing
/*
	*singularity
		name:The Singularity
		desc:Have <b>1</b> black hole extractor.
		req:1 bhExtractor
		icon:
*/
	*minuteMinutes
		name:Minute minutes
		desc:That's pronounced "my newt minits"<.>Play for <b>10 minutes</b>.
		req:10 minutesPlayed
		icon:numbers[1,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*minuteMaid
		name:Minute Maid
		desc:This maid has 60 whole minutes!<.>Play for <b>1 hour</b>.
		req:60 minutesPlayed
		icon:numbers[2,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*quarterDay
		name:Quarter day
		desc:Time is a valuable thing, you know.<.>Play for <b>6 hours</b>.
		req:360 minutesPlayed
		icon:numbers[3,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*halfDay
		name:Half day
		desc:Early release!<.>Play for <b>12 hours</b>.
		req:720 minutesPlayed
		icon:numbers[4,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*aDay
		name:A day
		desc:Watch the clock count down to the end of the day...<.>Play for <b>1 day</b>.
		req:1440 minutesPlayed
		icon:numbers[5,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*artificialLength
		name:Artificial length
		desc:play my game more please<.>Play for <b>3 and a half days</b>.
		req:5040 minutesPlayed
		icon:numbers[6,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*stillHere
		name:You're still here?
		desc:Watch time fly by as the pendulum swings.<.>Play for <b>1 week</b>.
		req:10080 minutesPlayed
		icon:https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
		icon:numbers[7,0] https://cdn.rawgit.com/morkysherk/3dc7a3dd52ec8ea422c58a57e25e5b02/raw/e55987c0e7926abe8d705c35284a36f8caccc471/clocke.svg
	*aBreak
		name:Taking a break
		desc:Avoid clicking for <b>1 hour</b>.
		req:3600 noClickSeconds
		icon:https://imgur.com/upPXJXm.png
	*dayOff
		name:Day off
		desc:Avoid clicking for <b>1 day</b>.
		req:86400 noClickSeconds
		icon:https://imgur.com/upPXJXm.png
	*3dayweekend
		name:3 day weekend
		desc:Avoid clicking for <b>3 days</b>.
		req:259200 noClickSeconds
		icon:https://imgur.com/upPXJXm.png
	*trueIdler
		name:True idler
		desc:Avoid clicking for <b>1 week</b>.
		req:604800 noClickSeconds
		icon:https://imgur.com/upPXJXm.png
	*hackerMan
		name:Hackerman
		desc:Enter any valid code.
		icon:https://cdn.rawgit.com/morkysherk/fa4681d23cc2ae43e1b4af31e2eb6163/raw/6334f33c614430626a18d45625e6d038218c0460/hax.svg

	*TEMPLATE
		no text
		class:smallThing
		on click:
			if (clickAnimation=1)
				anim icon wobble2
				anim wobble2
			end
			if (clickAnimation=2)
				anim icon bounceOnce
				anim bounceOnce
			end
			if (clickAnimation=3)
				anim icon plop
				anim plop
			end
			if (clickAnimation=4)
				anim icon wiggling2
				anim wiggling
			end
			if (clickAnimation=5)
				anim icon wobbleSlow
				anim wobbleSlow
			end
		end
		tag:secret
		on earn:yield 1 secretPoint
	*notaButton
		name:That's no button
		desc:What were you expecting?<//><.>Click the peanut butter cup.<.>Unlocks <b>peanut butter cup clicking.</b>
		icon:https://imgur.com/upPXJXm.png
		req:1 coolResource:earned
	*stop
		name:Stop that
		desc:What do you hope to accomplish?<//><.>Click the peanut butter cup <b>50</b> times.
		icon:numbers[2,0] https://imgur.com/upPXJXm.png
		req:50 coolResource:earned
	*whyThough
		name:Why though?
		desc:Just to get that secret counter up, I guess...<//><.>Click the peanut butter cup <b>250</b> times.<.>This is the last one by the way, don't waste your time
		icon:numbers[3,0] https://imgur.com/upPXJXm.png
		req:250 coolResource:earned
	*specificAchiev
		name:Unnecessarily specific
		desc:No way you figured this out on your own.<.>Have exactly <b>12</b> chocolate workers, <b>16</b> peas and nuts converters, and <b>22</b> replicators at once.<.>Enter code <b>[debugDigit1][debugDigit2][debugDigit3][debugDigit4]</b> to unlock the debug console.
		req:chocolateWorkers=12
		req:pbFactories=16
		req:replicators=22
		icon:https://cdn.rawgit.com/morkysherk/5270762fd925d1e6622f5fced5ee543a/raw/7d88db7faa827de23320dbe048802fcbbf3f6584/equal.svg
		tag:secret
	*statClicker
		name:Stat clicker
		desc:That wasn't so hard.<.>Click the stat <b>25</b> times.
		req:25 thisstatClicks
		on earn:hide thisstatClicks
		icon:https://cdn.rawgit.com/morkysherk/b80f99b9707d1237fb6a5b83027c700a/raw/6275c4b51d39b16b2e1a572edb6eec995ec778b3/cursor.svg
	*loss
		name:Loss
		desc:.jpg<.>At any time, use up more peanut butter or chocolate than you can produce.<.>Unlocks <b>gainful pain.</b>
		req:chocolate:ps<0 or peanutButter:ps<0
		icon:https://cdn.rawgit.com/morkysherk/12bdb209d5fcbde0d540346834e0e6a7/raw/6d942d564ab47a917fb2458ff657521b392ad5b6/menos.svg
		on earn:yield gainfulPain
/*
Somebody once told me the world is gonna roll me
I ain't the sharpest tool in the shed
She was looking kind of dumb with her finger and her thumb
In the shape of an "L" on her forehead
Well the years start coming and they don't stop coming
Fed to the rules and I hit the ground running
Didn't make sense not to live for fun
Your brain gets smart but your head gets dumb
So much to do, so much to see
So what's wrong with taking the back streets?
You'll never know if you don't go
You'll never shine if you don't glow
Hey now, you're an all-star, get your game on, go play
Hey now, you're a rock star, get the show on, get paid
And all that glitters is gold
Only shooting stars break the mold
It's a cool place and they say it gets colder
You're bundled up now, wait till you get older
But the meteor men beg to differ
Judging by the hole in the satellite picture
The ice we skate is getting pretty thin
The water's getting warm so you might as well swim
My world's on fire, how about yours?
That's the way I like it and I never get bored
Hey now, you're an all-star, get your game on, go play
Hey now, you're a rock star, get the show on, get paid
All that glitters is gold
Only shooting stars break the mold
Hey now, you're an all-star, get your game on, go play
Hey now, you're a rock star, get the show, on get paid
And all that glitters is gold
Only shooting stars
Somebody once asked could I spare some change for gas?
I need to get myself away from this place
I said yep what a concept
I could use a little fuel myself
And we could all use a little change
Well, the years start coming and they don't stop coming
Fed to the rules and I hit the ground running
Didn't make sense not to live for fun
Your brain gets smart but your head gets dumb
So much to do, so much to see
So what's wrong with taking the back streets?
You'll never know if you don't go (go!)
You'll never shine if you don't glow
Hey now, you're an all-star, get your game on, go play
Hey now, you're a rock star, get the show on, get paid
And all that glitters is gold
Only shooting stars break the mold
And all that glitters is gold
Only shooting stars break the mold
*/
