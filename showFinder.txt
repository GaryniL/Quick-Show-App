tell application "System Events"
	set activeApp to name of first application process whose frontmost is true
	if "Finder" is in activeApp then
		set visible of process "Finder" to false
	else
		
		tell application "Finder"
			
			tell application "Finder" to reopen
			tell application "Finder" to activate
			
			-- display dialog "my variable: " & (count Finder windows)
			if (count of Finder windows) = 0 then
				display dialog "my variable: " & (count Finder windows)
				-- check window nums
				tell application "Finder" to make new Finder window
			end if
			
		end tell
	end if
end tell

-- reopen -- unminimizes the first minimized window or makes a new default window
-- activate -- makes the app frontmost

-- try
-- 	set miniaturized of windows to false -- most apps
-- end try
-- try
--	set collapsed of windows to false -- Finder
-- end try