CMD:avukatyap(playerid, params[])
{
	if(PlayerData[playerid][pAdmin] < 2)
		return HataMesajGonder(playerid, "Yeterli yetkiniz yok!");

	static
	    userid;

	if (sscanf(params, "u", userid))
	    return KullanimMesajGonder(playerid, "/avukatyap [id/isim]");

	if (!IsPlayerConnected(userid) || GetPlayerState(userid) == PLAYER_STATE_SPECTATING || GetPlayerState(playerid) == PLAYER_STATE_SPECTATING)
	    return HataMesajGonder(playerid, "Bu oyuncu size yakin degil veya aktif degil.");

 	PlayerData[userid][pAvukat] = 1;
    BilgiMesajGonder(playerid, "%s adli oyuncuyu avukat yaptiniz.", ReturnName(userid, 0));
    BilgiMesajGonder(userid, "%s sizi avukat yapti.", ReturnName(playerid, 0));
    Oyuncu_Kaydet(userid);
	return 1;
}
CMD:avukatcikart(playerid, params[])
{
	if(PlayerData[playerid][pAdmin] < 2)
		return HataMesajGonder(playerid, "Yeterli yetkiniz yok!");

	static
	    userid;

	if (sscanf(params, "u", userid))
	    return KullanimMesajGonder(playerid, "/avukatcikart [id/isim]");

	if (!IsPlayerConnected(userid) || GetPlayerState(userid) == PLAYER_STATE_SPECTATING || GetPlayerState(playerid) == PLAYER_STATE_SPECTATING)
	    return HataMesajGonder(playerid, "Bu oyuncu size yakin degil veya aktif degil.");

 	PlayerData[userid][pAvukat] = 0;
    BilgiMesajGonder(playerid, "%s adli oyuncuyu avukatliktan cikarttiniz.", ReturnName(userid, 0));
    BilgiMesajGonder(userid, "%s sizi avukatliktan atti.", ReturnName(playerid, 0));
    Oyuncu_Kaydet(userid);
	return 1;
}
CMD:avukatlar(playerid, params[])
{
		new count = 0;

    SendClientMessage(playerid, COLOR_ADMINCHATT, "----------------------------------------");

    foreach (new i : Player) if (PlayerData[i][pAvukat] > 0)
	{

	 SendClientMessageEx(playerid, COLOR_ORANGE, "{BDBDBD}(Avukat) {FFFFFF}%s T. Numara: %d", ReturnName(i, 0), PlayerData[i][pTelefon]);

        count++;

	}
	if (!count) {
	    HataMesajGonder(playerid, "Aktif avukat yok.");
	}
	SendClientMessage(playerid, COLOR_ADMINCHATT, "----------------------------------------");
	return 1;
}
