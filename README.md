Cdoes-1 cmds copy by Dickinson
=======
CMD:changepass(playerid, params[])
{
	if (gPlayerLogged{playerid})
	{
		ShowPlayerDialog(playerid, 2398, DIALOG_STYLE_INPUT, "Password Change", "Please enter your new password!", "Change", "Exit" );
	}
	return 1;
}

CMD:killcheckpoint(playerid, params[])
{
    DeletePVar(playerid, "TrackCar");
    DisablePlayerCheckpoint(playerid);
	gPlayerCheckpointStatus[playerid] = CHECKPOINT_NONE;
 	TaxiCallTime[playerid] = 0;
  	BusCallTime[playerid] = 0;
  	SetPVarInt(playerid, "Pizza", 0);
    SendClientMessageEx(playerid,COLOR_WHITE,"All current checkpoints, trackers and accepted fares have been reset.");
	return 1;
}

CMD:help(playerid, params[])
{
	if(PlayerInfo[playerid][pLevel] <= 3)
	{
		SendClientMessageEx(playerid, TEAM_AZTECAS_COLOR,"*** HELP *** /report /requesthelp (/newb)ie /tognewbie");
	}
	SendClientMessageEx(playerid, COLOR_WHITE,"*** ACCOUNT *** /rules /faq /stats /inventory /myguns /buylevel /upgrade /changepass /killcheckpoint /resetupgrades(100k)");
	SendClientMessageEx(playerid, COLOR_WHITE,"*** CHAT *** /w(hisper) /o(oc) /s(hout) /l(ow) /b /ad(vertise) /f(amily) /me /togooc /tognews /togfam /togwhisper");
	SendClientMessageEx(playerid, COLOR_WHITE,"*** BANK *** /balance /withdraw /deposit /wiretransfer /abalance /awithdraw /adeposit /awiretransfer");
	SendClientMessageEx(playerid, COLOR_WHITE,"*** GENERAL *** /pay /writecheck /cashchecks /charity /time /buy /id /music /showlicenses /clothes /mywarrants");
	SendClientMessageEx(playerid, COLOR_WHITE,"*** GENERAL *** /lock /skill /stopani /do /me /kill /buyclothes /droplicense /calculate /refuel /car /seatbelt /checkbelt");
	SendClientMessageEx(playerid, COLOR_WHITE,"*** GENERAL *** /cancel /accept /eject /usepot /usecrack /contract /service /families /joinevent /checkweed");


	switch(PlayerInfo[playerid][pJob])
	{
		case 1: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /find");
		case 2: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /lawyerduty /free /defend /wanted /offerappeal /finishappeal");
		case 3: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /sex");
		case 4: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /sellpot /sellcrack /getcrack /getseeds /plantseeds /pickweed /checkweed");
		case 5: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /dropcar");
		case 7: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /fix /nos /hyd /repair /refill /mechduty");
		case 8: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /guard /frisk");
		case 9: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getmats /sellmats /sellgun");
		case 10: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /sellnewcar");
		case 12: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /fight");
		case 14: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getcrate");
		case 15: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /papers /bring /deliver");
		case 17: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /fare");
		case 18: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getmats /sellmats /craft");
		case 19: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /selldrink");
		case 20: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /loadtruck /checktruck /hijacktruck");
		case 21: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getpizza");
	}
	switch(PlayerInfo[playerid][pJob2])
	{
		case 1: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /find");
		case 2: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /lawyerduty /free /defend /wanted");
		case 3: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /sex");
		case 4: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /sellpot /sellcrack /getcrack /getseeds /plantseeds /pickweed /checkweed");
		case 5: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /dropcar");
		case 7: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /fix /nos /hyd /repair /refill /mechduty");
		case 8: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /guard /frisk");
		case 9: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getmats /sellmats /sellgun");
		case 10: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /sellnewcar");
		case 12: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /fight");
		case 14: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getcrate");
		case 15: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /papers /bring /deliver");
		case 17: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /fare");
		case 18: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getmats /sellmats  /craft");
		case 19: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /selldrink");
		case 20: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /loadtruck /checktruck /hijacktruck");
		case 21: SendClientMessageEx(playerid,COLOR_WHITE,"*** JOB *** /getpizza");
	}
	switch(PlayerInfo[playerid][pMember])
	{
		case 1:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** LSPD *** (/r)adio (/d)epartments (/m)egaphone (/su)spect /lspd /mdc /detain /arrest /warrantarrest /wanted /cuff /tazer /cam");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** LSPD *** /frisk /take /ticket (/gov)ernment /clothes /ram /invite /giverank /deployspikes /destroyspikes /spikestrip /wants");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** LSPD *** /deploycade /destroycade /revokedl /vcheck /vmdc /vticket /tow /untow /impound /lspddiv /destroyplant /radargun /searchcar");
		}
		case 2:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FBI *** (/r)adio (/d)epartments (/m)egaphone (/su)spect /fbi /mdc /detain /arrest /warrantarrest /wanted /cuff /tazer /bug /togbr");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FBI *** /frisk /take /ticket (/gov)ernment /clothes /ram /invite /giverank /deployspikes /destroyspikes /spikestrip /wants /searchcar");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FBI *** /deploycade /destroycade /revokedl /revokeairdl /vcheck /vmdc /vticket /tow /untow /impound /fbidiv /destroyplant /radargun");
		}
		case 3:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** SFPD *** (/r)adio (/d)epartments (/m)egaphone (/su)spect /sfpd /mdc /detain /arrest /warrantarrest /jarrest /wanted /cuff /tazer /wants");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** SFPD *** /frisk /take /ticket (/gov)ernment /deliver /clothes /ram /invite /giverank /deployspikes /destroyspikes /spikestrip /present");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** SFPD *** /deploycade /destroycade /revokedl /vcheck /vmdc /vticket /tow /untow /impound /sfpddiv /destroyplant /radargun /searchcar");
		}
		case 4:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FDSA *** (/r)adio (/d)epartments (/m)egaphone /heal /clothes /invite /giverank /fdsa /revokeboatdl /fdsadiv");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FDSA *** /getpt /movept /loadpt /deliverpt /destroyplant");
		}
		case 5:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** JUDICIAL SYSTEM *** (/r)adio (/d)epartments /warrant /warrantwd /judgefine /judgejail /judgeprison /probation /wants");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** JUDICIAL SYSTEM *** /invite /uninvite /giverank /trial /adjourn /sentence /reward /checkjudgements /reversejudgement /present");
		}
		case 6:
		{
			if(PlayerInfo[playerid][pRank] < 3)
			{
				SendClientMessageEx(playerid, COLOR_WHITE, "*** GOVERNMENT *** (/r)adio (/d)epartments (/se)nate /mdc /deployspikes /spikestrip");
			}
			else
			{
				SendClientMessageEx(playerid, COLOR_WHITE, "*** GOVERNMENT *** (/r)adio (/d)epartments (/se)nate /settax /checktax /taxwithdraw /invite /giverank (/gov)ernment (/su)spect");
				SendClientMessageEx(playerid, COLOR_WHITE, "*** GOVERNMENT *** /mdc /detain /arrest /wanted /cuff /tazer /frisk /take /ticket /clothes /ram /invite /giverank");
				SendClientMessageEx(playerid, COLOR_WHITE, "*** GOVERNMENT *** /spikestrip /destroyplant /radargun /warrantarrest /pardon /commute /wants /deployspikes /destroyspikes");
			}
		}
		case 7:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** SASD *** (/r)adio (/d)epartments (/m)egaphone (/su)spect /sasd /mdc /detain /arrest /warrantarrest /wanted /cuff /tazer");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** SASD *** /frisk /take /ticket (/gov)ernment /clothes /ram /invite /giverank /deployspikes /destroyspikes /spikestrip /wants");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** SASD *** /deploycade /destroycade /revokedl /vcheck /vmdc /vticket /tow /untow /impound /sasddiv /destroyplant /searchcar");
		}
		case 8:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** HITMAN AGENCY *** (/f)amily /contracts /givemehit /order /ranks /profile");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** HITMAN AGENCY *** /plantbomb /plantcarbomb /pickupbomb /clothes /invite /giverank /showmehq /showmehq2 /showmehq3");
		}
		case 9:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NEWS AGENCY *** /live /nr [text] /broadcast /cameraangle /clothes /invite /giverank /lockhq /liveban /newsdiv");
		}
		case 10:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** TAXI *** /fare /clothes /invite /giverank");
		}
		case 11:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NG *** /r /d /mdc /backup /tazer /ram /shutdown /take /frisk /radargun /(un)cuff /detain /ticket /su");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NG *** /wanted /checkjudgements /wants /warrantarrest /destroyplant /vmdc /vticket /vcheck /searchcar");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NG *** /spikestrip /deploy(destroy)cade /deploy(destroy)spikes /(no)backup /gov /ngdiv /showmeship /ndeliver");
		}
		case 12:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** TIERRA ROBADA *** (/r)adio /trlocker /trdiv /clothes /invite /uninvite /giverank /gov /showbadge");
			if(PlayerInfo[playerid][pDivision] == 2)
			{
				SendClientMessageEx(playerid, COLOR_WHITE, "*** TIERRA ROBADA ARMED FORCES *** (/m)egaphone /tazer /detain /cuff /arrest /ticket /frisk");
			}
			if(PlayerInfo[playerid][pDivision] == 3)
			{
				SendClientMessageEx(playerid, COLOR_WHITE, "*** TIERRA ROBADA EMERGENCY SERVICES *** (/m)egaphone /heal /movept /loadpt /deliverpt");
			}
		}
		case 13:
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NOOSE *** (/r)adio (/d)epartments (/m)egaphone (/su)spect /noose /mdc /detain /arrest /warrantarrest /wanted /cuff /tazer");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NOOSE *** /frisk /take /ticket /ram /invite /giverank /deployspikes /destroyspikes /spikestrip /wants");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** NOOSE *** /deploycade /destroycade /vcheck /vmdc /destroyplant /radargun /searchcar");
		}
	}
	if (PlayerInfo[playerid][pFMember] != 255)
	{
		if(PlayerInfo[playerid][pRank] < 5)
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FAMILY *** (/f)amily /clothes /safehelp /movegate");
		}
		else
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FAMILY *** (/f)amily /clothes /safehelp /movegate /fdeposit /fwithdraw /fbalance /claim /capture /adjust");
			SendClientMessageEx(playerid, COLOR_WHITE, "*** FAMILY *** /gpark /gvlock /gbuylock");
		}
	}
	if (PlayerInfo[playerid][pAdmin] >= 1)
	{
		SendClientMessageEx(playerid, COLOR_WHITE, "*** ADMIN *** (/a)dmin (/ah)elp");
	}
	if (PlayerInfo[playerid][pHelper] >= 1)
	{
		SendClientMessageEx(playerid, COLOR_WHITE, "*** COMMUNITY ADVISOR *** (/ch)elp");
	}
	if(PlayerInfo[playerid][pDonateRank] >= 1)
	{
		SendClientMessageEx(playerid, COLOR_PURPLE, "*** VIP *** /travel /viplocker /tokenhelp /buddyinvite /phoneprivacy /setautoreply");
	}
	if(PlayerInfo[playerid][pDonateRank] == 5)
	{
		SendClientMessageEx(playerid, COLOR_PURPLE, "*** VIP Moderator *** /vipparty /vto /vtoreset /vmute /vsuspend");
	}
	SendClientMessageEx(playerid, COLOR_WHITE,"*** OTHER *** /cellphonehelp /carhelp /househelp /toyhelp /renthelp /jobhelp /leaderhelp /animhelp /fishhelp /insurehelp");
	return 1;
}

CMD:showmeship(playerid, params[])
{
    if(PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11)
	{
	    new Float:X, Float:Y, Float:Z;
	    GetObjectPos(Carrier[0], X, Y, Z);
	    SetPlayerCheckpoint(playerid,X, Y, Z, 4.0);
		GameTextForPlayer(playerid, "~w~Waypoint set ~r~USS Nimitz", 5000, 1);
	}
	return 1;
}

CMD:resetcarrier(playerid, params[])
{
	if(PlayerInfo[playerid][pLeader] == 11 && PlayerInfo[playerid][pRank] == 6)
	{
	    if(GetPVarInt(playerid, "dccConfirm") == 0)
	    {
	        SetPVarInt(playerid, "dccConfirm", 1);
	        SendClientMessageEx(playerid, COLOR_WHITE, "Use of this command will fully reset the carrier to its original position");
	        SendClientMessageEx(playerid, COLOR_WHITE, "If you are sure you want to do this, please re-type the command (/resetcarrier)");
	    }
	    else
	    {
	        SetPVarInt(playerid, "dccConfirm", 0);

	        SendClientMessageEx(playerid, COLOR_WHITE, "* Unloading Vehicles");
	        UnloadNGVehicles();

	        SendClientMessageEx(playerid, COLOR_WHITE, "* Destroying Objects");
			DestroyDynamicObject(sidelift);
			DestroyDynamicObject(backhatch);
			DestroyDynamicObject(backlift);
			for(new x;x<sizeof(Carrier);x++)
			{
			    DestroyObject(Carrier[x]);
			}
			for(new x;x<sizeof(CarrierS);x++)
			{
			    DestroyDynamicObject(CarrierS[x]);
			}

			SendClientMessageEx(playerid, COLOR_WHITE, "* Re-Building Carrier");
			sidelift = CreateDynamicObject(3114, 231.916656, 3615.134277, 17.269205, 0.0000, 0.0000, 0.0000); // Side Lift Up
			backhatch = CreateDynamicObject(3113, 180.344864, 3600.390137, 2.516232, 0.0000, 0.0000, 0.0000); // Back Hatch Closed
			backlift = CreateDynamicObject(3115, 189.694626, 3599.983398, 17.483730, 0.0000, 0.0000, 0.0000); // Back Lift Up

			Carrier[0] = CreateObject(10771, 288.665771, 3600.003418, 6.032381, 0.0000, 0.0000, 0.0000, 300);
			Carrier[1] = CreateObject(11145, 225.782196, 3600.015137, 4.754915, 0.0000, 0.0000, 0.0000, 300);
			Carrier[2] = CreateObject(11149, 282.526093, 3594.805176, 12.487646, 0.0000, 0.0000, 0.0000, 300);
			Carrier[3] = CreateObject(11146, 279.620544, 3600.541016, 12.893089, 0.0000, 0.0000, 0.0000, 300);
			Carrier[4] = CreateObject(10770, 291.858917, 3592.397949, 39.171509, 0.0000, 0.0000, 0.0000, 300);
			Carrier[5] = CreateObject(10772, 290.014313, 3599.787598, 17.833616, 0.0000, 0.0000, 0.0000, 300);
			Carrier[6] = CreateObject(1671, 354.860748, 3589.442383, 11.234554, 0.0000, 0.0000, 175.3254, 300);
			Carrier[7] = CreateObject(925, 304.330383, 3589.067383, 11.735489, 0.0000, 0.0000, 0.0000, 300);
			Carrier[8] = CreateObject(930, 301.851654, 3588.497070, 11.131838, 0.0000, 0.0000, 0.0000, 300);
			Carrier[9] = CreateObject(930, 301.856079, 3589.598145, 11.181837, 0.0000, 0.0000, 0.0000, 300);
			Carrier[10] = CreateObject(964, 300.513062, 3589.303711, 10.705961, 0.0000, 0.0000, 177.4217, 300);
			Carrier[11] = CreateObject(964, 299.024902, 3589.362793, 10.698584, 0.0000, 0.0000, 177.4217, 300);
			Carrier[12] = CreateObject(1271, 305.058319, 3591.442871, 11.048584, 0.0000, 0.0000, 359.1406, 300);
			Carrier[13] = CreateObject(1431, 303.009491, 3591.383789, 11.253574, 0.0000, 0.0000, 0.0000, 300);
			Carrier[14] = CreateObject(2567, 297.100800, 3591.239746, 12.558563, 0.0000, 0.0000, 91.1003, 300);
			Carrier[15] = CreateObject(3576, 301.050110, 3593.777344, 12.198634, 0.0000, 0.0000, 0.0000, 300);
			Carrier[16] = CreateObject(3633, 304.567841, 3593.262207, 11.173386, 0.0000, 0.0000, 0.0000, 300);

			CarrierS[0] = CreateDynamicObject(3267, 320.358582, 3592.519043, 21.567169, 0.0000, 0.0000, 0.0000);
			CarrierS[1] = CreateDynamicObject(11237, 291.557526, 3592.407715, 39.065594, 0.0000, 0.0000, 0.0000);
			CarrierS[2] = CreateDynamicObject(3395, 354.861725, 3590.989746, 10.797120, 0.0000, 0.0000, 88.0403);
			CarrierS[3] = CreateDynamicObject(1671, 356.571838, 3588.612793, 11.234554, 0.0000, 0.0000, 134.9316);
			CarrierS[4] = CreateDynamicObject(3393, 358.360016, 3588.834961, 10.797121, 0.0000, 0.0000, 0.0000);
			CarrierS[5] = CreateDynamicObject(3277, 320.391876, 3592.538086, 21.514416, 0.0000, 0.0000, 164.0483);

			SendClientMessageEx(playerid, COLOR_WHITE, "* Re-Loading Vehicles");
			LoadNGVehicles();

			SendClientMessageEx(playerid, COLOR_WHITE, "* Saving Carrier");
			SaveCarrier();

			SendClientMessageEx(playerid, COLOR_WHITE, "* Done!");
		}
	}
	return 1;
}

CMD:control(playerid, params[])
{
    if(PlayerInfo[playerid][pLeader] == 11 && PlayerInfo[playerid][pRank] == 6)
	{
		if(control[playerid] == 1)
		{
		    TogglePlayerControllable(playerid, true);
		    SetCameraBehindPlayer(playerid);
		    KillTimer(ControlTimer[playerid]);
		    LoadNGVehicles();
		    SaveCarrier();
	  		control[playerid] = 0;
	   		SendClientMessageEx(playerid, COLOR_WHITE, "You are no longer controlling the Aircraft Carrier");
		}
		else
		{
		    UnloadNGVehicles();
	     	new Float:X, Float:Y, Float:Z;
		    GetObjectPos(Carrier[0], X, Y, Z);
		    SetPlayerCameraPos(playerid, X-200, Y, Z+40);
		    SetPlayerCameraLookAt(playerid, X, Y, Z);
		    TogglePlayerControllable(playerid, false);
		    ControlTimer[playerid] = SetTimerEx("ControlCam", 1000, true, "i", playerid);
		    control[playerid] = 1;
	   		controlspeed[playerid] = 25;
	  		controldistance[playerid] = 50;
		   	SendClientMessageEx(playerid, COLOR_WHITE, "You are now controlling the Aircraft Carrier with Speed 50, Distance 100");
		}
	}
	return 1;
}

CMD:bldown(playerid, params[])
{
    new string[30 + MAX_PLAYER_NAME], Float:X, Float:Y, Float:Z;
    GetDynamicObjectPos(backlift, X, Y, Z);
   	if(IsPlayerInRangeOfPoint(playerid, 50, X, Y, Z) && (PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11))
    {
    	if(canmove == 1) return 1;
	    format(string, sizeof(string), "* %s moves down the back lift.", GetPlayerNameEx(playerid));
		ProxDetector(50.0, playerid, string, COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE);

		MoveDynamicObject (backlift,X, Y, 10.435794,1); // Back Lift (down position)
	}
	return 1;
}

CMD:blup(playerid, params[])
{
    new string[30 + MAX_PLAYER_NAME], Float:X, Float:Y, Float:Z;
    GetDynamicObjectPos(backlift, X, Y, Z);
    if(IsPlayerInRangeOfPoint(playerid, 50, X, Y, Z) && (PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11))
    {
    	if(canmove == 1) return 1;
    	format(string, sizeof(string), "* %s moves up the back lift.", GetPlayerNameEx(playerid));
		ProxDetector(50.0, playerid, string, COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE);
		MoveDynamicObject (backlift,X, Y, 17.483730,1); // Back Lift (up position)
	}
	return 1;
}

CMD:sldown(playerid, params[])
{
    new string[30 + MAX_PLAYER_NAME], Float:X, Float:Y, Float:Z;
    GetDynamicObjectPos(sidelift, X, Y, Z);
    if(IsPlayerInRangeOfPoint(playerid, 50, X, Y, Z) && (PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11))
    {
    	if(canmove == 1) return 1;
	    format(string, sizeof(string), "* %s moves down the side lift.", GetPlayerNameEx(playerid));
		ProxDetector(50.0, playerid, string, COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE);
		MoveDynamicObject (sidelift,X, Y, 10.271654,1); // Side Lift (down position)
	}
	return 1;
}

CMD:slup(playerid, params[])
{
	new string[30 + MAX_PLAYER_NAME], Float:X, Float:Y, Float:Z;
    GetDynamicObjectPos(sidelift, X, Y, Z);
    if(IsPlayerInRangeOfPoint(playerid, 50, X, Y, Z) && (PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11))
    {
    	if(canmove == 1) return 1;
	    format(string, sizeof(string), "* %s moves up the side lift.", GetPlayerNameEx(playerid));
		ProxDetector(50.0, playerid, string, COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE);
		MoveDynamicObject (sidelift,X, Y, 17.269205,1); // Side Lift (down position)
	}
	return 1;
}

CMD:bhdown(playerid, params[])
{
    new string[30 + MAX_PLAYER_NAME], Float:X, Float:Y, Float:Z;
    GetDynamicObjectPos(backhatch, X, Y, Z);
   	if(IsPlayerInRangeOfPoint(playerid, 50, X, Y, Z) && (PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11))
    {
		if(canmove == 1) return 1;
   		format(string, sizeof(string), "* %s moves down the back hatch.", GetPlayerNameEx(playerid));
		ProxDetector(50.0, playerid, string, COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE);
		MoveDynamicObject (backhatch, X, Y, 2.516232,1); // Back Hatch (down position)
	}
	return 1;
}

CMD:bhup(playerid, params[])
{
    new string[128], Float:X, Float:Y, Float:Z;
    GetDynamicObjectPos(backhatch, X, Y, Z);
    if(IsPlayerInRangeOfPoint(playerid, 50, X, Y, Z) && (PlayerInfo[playerid][pMember] == 11 || PlayerInfo[playerid][pLeader] == 11))
    {
    	if(canmove == 1) return 1;
	    format(string, sizeof(string), "* %s moves up the back hatch", GetPlayerNameEx(playerid));
		ProxDetector(50.0, playerid, string, COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE,COLOR_PURPLE);
		MoveDynamicObject (backhatch,X, Y, 17.280232,1); // Back Hatch (up position)
	}
	else
	{
	    SendClientMessageEx(playerid, COLOR_GRAD2, "* You are not near the back lift");
	}
	return 1;
}

CMD:badge(playerid, params[]) {
    if((IsACop(playerid) || PlayerInfo[playerid][pMember] == 4 || PlayerInfo[playerid][pLeader] == 4 || PlayerInfo[playerid][pMember] == 12 || PlayerInfo[playerid][pLeader] == 12) && GetPVarInt(playerid, "IsInArena") < 0 && !GetPVarInt(playerid, "EventToken") && PlayerInfo[playerid][pJailed] == 0 || PlayerInfo[playerid][pMember] == 9 && PlayerInfo[playerid][pDivision] == 1) {
		if(PlayerInfo[playerid][pDuty]) {
			PlayerInfo[playerid][pDuty] = 0;
			SetPlayerToTeamColor(playerid);
			SendClientMessageEx(playerid, COLOR_WHITE, "You have hidden your badge, and will now be identified as being off-duty.");
		}
		else {
			PlayerInfo[playerid][pDuty] = 1;
			SetPlayerToTeamColor(playerid);
			SendClientMessageEx(playerid, COLOR_WHITE, "You have shown your badge, and will now be identified as being on-duty.");
		}
	}
	return 1;
}

CMD:car(playerid, params[])
{
	if(isnull(params))
	{
		SendClientMessageEx(playerid, COLOR_WHITE, "USAGE: /car [name]");
		SendClientMessageEx(playerid, COLOR_GREY, "Available names: Status, Engine, Lights, Trunk, Hood, Fuel");
		return 1;
	}
	if(strcmp(params, "engine", true) == 0 && IsPlayerInAnyVehicle(playerid) && GetPlayerState(playerid) == PLAYER_STATE_DRIVER)
	{
		new engine,lights,alarm,doors,bonnet,boot,objective,vehicleid;
		vehicleid = GetPlayerVehicleID(playerid);
		if(GetVehicleModel(vehicleid) == 481 || GetVehicleModel(vehicleid) == 509 || GetVehicleModel(vehicleid) == 510) return SendClientMessageEx(playerid,COLOR_WHITE,"This command can't be used in this vehicle.");
		GetVehicleParamsEx(vehicleid,engine,lights,alarm,doors,bonnet,boot,objective);
		if(engine == VEHICLE_PARAMS_ON)
		{
			SetVehicleEngine(vehicleid, playerid);
		}
		else if((engine == VEHICLE_PARAMS_OFF || engine == VEHICLE_PARAMS_UNSET))
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "Vehicle engine starting, please wait...");
			SetTimerEx("SetVehicleEngine", 1000, 0, "dd",  vehicleid, playerid);
		}
	}
	else if(strcmp(params, "lights", true) == 0 && IsPlayerInAnyVehicle(playerid) && GetPlayerState(playerid) == PLAYER_STATE_DRIVER)
	{
		new vehicleid = GetPlayerVehicleID(playerid);
		if(GetVehicleModel(vehicleid) == 481 || GetVehicleModel(vehicleid) == 509 || GetVehicleModel(vehicleid) == 510) return SendClientMessageEx(playerid,COLOR_WHITE,"This command can't be used in this vehicle.");
		SetVehicleLights(vehicleid, playerid);
	}
	else if(strcmp(params, "hood", true) == 0 && IsPlayerInAnyVehicle(playerid) && GetPlayerState(playerid) == PLAYER_STATE_DRIVER)
	{
		if(IsPlayerInAnyVehicle(playerid) && GetPlayerState(playerid) == PLAYER_STATE_DRIVER)
		{
			new vehicleid = GetPlayerVehicleID(playerid);
			if(GetVehicleModel(vehicleid) == 481 || GetVehicleModel(vehicleid) == 509 || GetVehicleModel(vehicleid) == 510 || IsAPlane(vehicleid) || IsABike(vehicleid))
			{
				return SendClientMessageEx(playerid,COLOR_WHITE,"This command can't be used in this vehicle.");
			}
			SetVehicleHood(vehicleid, playerid);
		}
		else if(!IsPlayerInAnyVehicle(playerid))
		{
			new closestcar = GetClosestCar(playerid);
			if(IsPlayerInRangeOfVehicle(playerid, closestcar, 5.0))
			{
				if(GetVehicleModel(closestcar) == 481 || GetVehicleModel(closestcar) == 509 || GetVehicleModel(closestcar) == 510 || IsAPlane(closestcar) || IsABike(closestcar))
				{
					return SendClientMessageEx(playerid,COLOR_WHITE,"This command can't be used on this vehicle.");
				}
				SetVehicleHood(closestcar, playerid);
			}
		}
	}
	else if(strcmp(params, "trunk", true) == 0)
  	{
		if(IsPlayerInAnyVehicle(playerid) && GetPlayerState(playerid) == PLAYER_STATE_DRIVER)
		{
			new vehicleid = GetPlayerVehicleID(playerid);
			if(GetVehicleModel(vehicleid) == 481 || GetVehicleModel(vehicleid) == 509 || GetVehicleModel(vehicleid) == 510)
			{
				return SendClientMessageEx(playerid,COLOR_WHITE,"This command can't be used in this vehicle.");
			}
			SetVehicleTrunk(vehicleid, playerid);
		}
		else if(!IsPlayerInAnyVehicle(playerid))
		{
			new closestcar = GetClosestCar(playerid);
			if(IsPlayerInRangeOfVehicle(playerid, closestcar, 5.0))
			{
				if(GetVehicleModel(closestcar) == 481 || GetVehicleModel(closestcar) == 509 || GetVehicleModel(closestcar) == 510)
				{
					return SendClientMessageEx(playerid,COLOR_WHITE,"This command can't be used on this vehicle.");
				}
				SetVehicleTrunk(closestcar, playerid);
			}
		}
	}
	else if(strcmp(params, "fuel", true) == 0 && IsPlayerInAnyVehicle(playerid))
	{
		if(GetVehicleModel(GetPlayerVehicleID(playerid)) == 481 || GetVehicleModel(GetPlayerVehicleID(playerid)) == 509 || GetVehicleModel(GetPlayerVehicleID(playerid)) == 510) return SendClientMessageEx(playerid,COLOR_RED,"This vehicle doesn't need fuel.");
		if(GetPVarInt(playerid, "fuelonoff") == 0)
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "You have turned on the fuel indicator (green bar).");
			SetPVarInt(playerid, "fuelonoff", 1);
			FuelBar[playerid] = CreateProgressBar(548.00, 26.00, 57.50, 3.20, 866792447, 100.0);
			textdrawscount++;
			SetProgressBarValue(FuelBar[playerid], VehicleFuel[GetPlayerVehicleID(playerid)]);
			ShowProgressBarForPlayer(playerid, FuelBar[playerid]);
		}
		else
		{
			SendClientMessageEx(playerid, COLOR_WHITE, "You have turned off the fuel indicator (green bar).");
			SetPVarInt(playerid, "fuelonoff", 0);
			DestroyProgressBar(FuelBar[playerid]);
			textdrawscount--;
			FuelBar[playerid] = INVALID_BAR_ID;
		}
	}
	else if(strcmp(params, "status", true) == 0)
	{
		if(IsPlayerInAnyVehicle(playerid) && GetPlayerState(playerid) == PLAYER_STATE_DRIVER)
		{
			new vehicleid = GetPlayerVehicleID(playerid);
			new engine,lights,alarm,doors,bonnet,boot,objective,enginestatus[4],lightstatus[4], string[48];
			GetVehicleParamsEx(vehicleid,engine,lights,alarm,doors,bonnet,boot,objective);
			if(GetVehicleModel(vehicleid) == 481 || GetVehicleModel(vehicleid) == 509 || GetVehicleModel(vehicleid) == 510) return SendClientMessageEx(playerid,COLOR_RED,"This vehicle doesn't need fuel.");
			if(engine != VEHICLE_PARAMS_ON) format(enginestatus, sizeof(enginestatus), "OFF");
			else format(enginestatus, sizeof(enginestatus), "ON");
			if(lights != VEHICLE_PARAMS_ON) format(lightstatus, sizeof(lightstatus), "OFF");
			else format(lightstatus, sizeof(lightstatus), "ON");
			format(string, sizeof(string), "Engine: %s | Lights: %s | Fuel: %.2f.",enginestatus,lightstatus,VehicleFuel[vehicleid]);
			SendClientMessageEx(playerid, COLOR_WHITE, string);
		}
	}
	return 1;
}
