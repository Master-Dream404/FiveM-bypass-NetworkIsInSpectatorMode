# FiveM-bypass-NetworkIsInSpectatorMode-using-C-
this is a way you can bypass server anticheats that checks NetworkIsInSpectatorMode.

example:
```
if (NetworkIsInSpectatorMode() == 1) then
TriggerServerEvent('ban', "anti Spectator")
end
```

Process:
```
FiveM_b2699_GameProcess.exe+1124231 - 66 89 81 28050000 - mov [rcx+00000528],ax
set ax to 0 bytes for this: "FiveM_b2699_GameProcess.exe+1124231 - C7 81 28050000 00000000"
```
function:
```ida
__int16 __fastcall sub_1124228(__int64 a1, __int16 a2)
{
//a1 = class
//a2 = result | true, false true = 1 false = 0/false
  __int16 result; // ax

  result = 0;
  if ( a2 )
    result = a2;
  *(_WORD *)(a1 + 1320) = result;//set NetworkIsInSpectatorMode
  return result;
}
```
video: https://www.youtube.com/watch?v=411lUFPUwkk
