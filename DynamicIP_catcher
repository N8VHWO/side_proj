on getmyIp()
	set myRecord to do shell script "curl https://api.myip.com"
	set ipEnd to offset of "country" in myRecord
	(*if ipEnd is equal to "" then
		display dialog "FCKN SSL handshake failed"  buttons {"FUCK!", "Repeat"} default button "Repeat"
		if the button returned of the result is "Repeat" then
			display dialog "FUUU"
		end if *)
	if ipEnd is equal to 0 then
		display dialog "FCKN SSL handshake failed" buttons {"FUCK!", "Repeat"} default button "Repeat"
		if the button returned of the result is "Repeat" then
			return getmyIp()
		else
			quit
		end if
	else
		text 8 thru (ipEnd - 4) of myRecord
	end if
end getmyIp
getmyIp()

(*on getchatID()
	set myRecord to do shell script "curl https://api.telegram.org/bot6204259606:AAFiBDbJon05qq9RVeRs0KSCNnz4NXe2Z8c/getUpdates"
	set idStart to offset of "chat\":{\"id\":" in myRecord
	text (idStart + 12) thru (idStart + 20) of myRecord
end getchatID
getchatID()*)
set myIp to getmyIp()
set chatID to "105877486"
set tMsg to "https://api.telegram.org/bot6204259606:AAFiBDbJon05qq9RVeRs0KSCNnz4NXe2Z8c/sendMessage?chat_id=" & chatID & "&text=" & myIp
to goToWebPage(theWebPage)
	tell application "Safari"
		set URL of document 1 to theWebPage
	end tell
end goToWebPage

goToWebPage(tMsg)

on quit
	display dialog ¬
		"Really quit?" buttons {"No", "Quit"} default button "Quit"
	if the button returned of the result is "Quit" then
		continue quit
	end if
end quit
