--[[

DrawDamageLib---Damage data from Deftsu DamageLib!
   Thank Deftsu
!

                         by SoulKingLHW 
]]--


require('Inspired')
require("DamageLib")
 
OnDraw(function(myHero)
		for I = 1, #heroes do
			local unit = heroes[I]
			if ValidTarget(unit) then
				local barPos = GetHPBarPos(unit)
				if barPos.x > 0 and barPos.y > 0 then
		 	     	local str={_Q, _W, _E, _R}
					local mhp = GetMaxHP(unit)
					local chp = GetCurrentHP(unit)
					local offset = 103 * (chp/mhp)
					for M, spell in pairs({"Q", "W", "E", "R"}) do
						if getdmg(spell,unit) > 0 and IsReady(str[M]) then
							local off = 103*(getdmg(spell,unit)/mhp)
							local M = 2*M
							DrawLine(barPos.x+1+offset-off, barPos.y-1, barPos.x+1+offset, barPos.y-1, 5, 0xDFFFE258)
							DrawLine(barPos.x+1+offset-off, barPos.y-1, barPos.x+1+offset-off, barPos.y+10-10*M, 1, 0xDF8866F4)
							DrawText(spell, 11, barPos.x+1+offset-off, barPos.y-5-10*M, 0xDF55F855)
							DrawText(""..getdmg(spell,unit), 10, barPos.x+4+offset-off, barPos.y+5-10*M, 0xDFFF5858)
							offset = offset - off
						end
					end
				end
			end
		end

	end)
