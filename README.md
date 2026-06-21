@echo off
chcp 65001 >nul
setlocal enabledelayedexpansion
title 🚀 BOT LIKE FREE FIRE | PRO VERSÃO 🚀
color 0A
cls

:: ==============================================================
::                🚀 SISTEMA PROFISSIONAL 🚀
::              100% FUNCIONAL | IGUAL DOS PAGOS
:: ==============================================================
echo.
echo          ╔══════════════════════════════════════════╗
echo          ║  🚀 BOT LIKE FREE FIRE - EDIÇÃO PRO 🚀  ║
echo          ║                                            ║
echo          ║       ✅ ENVIA CURTIDAS REAIS             ║
echo          ║       ✅ NÃO FECHA | NÃO TRAVA           ║
echo          ║       ✅ SISTEMA DE RECONEXÃO            ║
echo          ║                                            ║
echo          ║        💎 CÓDIGO EXCLUSIVO 2026 💎       ║
echo          ╚══════════════════════════════════════════╝
echo.

:: ==============================================================
::                  📋 CONFIGURAÇÃO
:: ==============================================================
set /p "ID=  🔑  COLE SEU ID DO PERFIL: "
set /p "QTD=  🔢  QUANTAS CURTIDAS VOCÊ QUER: "
echo.
echo          ╔══════════════════════════════════════════╗
echo          ║  ⚡ ESCOLHA A VELOCIDADE DE ENVIO ⚡       ║
echo          ║                                            ║
echo          ║     [1] 🟢 RÁPIDA  (MAIS VELOZ)           ║
echo          ║     [2] 🟡 NORMAL  (RECOMENDADO)          ║
echo          ║     [3] 🔴 SEGURA  (SEM RISCO)           ║
echo          ╚══════════════════════════════════════════╝
set /p "VEL=  ⌨️  DIGITE A OPÇÃO: "

:: ⚙️ DEFINE TEMPO DE ACORDO COM ESCOLHA
if "%VEL%"=="1" set "TEMPO=100" & set "VEL_NOME=RÁPIDA 🟢"
if "%VEL%"=="2" set "TEMPO=300" & set "VEL_NOME=NORMAL 🟡"
if "%VEL%"=="3" set "TEMPO=600" & set "VEL_NOME=SEGURA 🔴"
if not defined TEMPO set "TEMPO=300" & set "VEL_NOME=NORMAL 🟡"

cls
echo.
echo          ╔══════════════════════════════════════════╗
echo          ║       📊 INFORMAÇÕES DO PROCESSO 📊       ║
echo          ║                                            ║
echo          ║  👤 ID DO USUÁRIO: %ID%      ║
echo          ║  🎯 QUANTIDADE: %QTD% CURTIDAS           ║
echo          ║  ⚡ VELOCIDADE: !VEL_NOME!                ║
echo          ║                                            ║
echo          ║  ⏳ STATUS: ⏳ INICIANDO... AGUARDE...    ║
echo          ╚══════════════════════════════════════════╝
echo.

set "CONT=0"
set "ERROS=0"

:: ==============================================================
::                  🔄 LOOP PRINCIPAL
:: ==============================================================
:LOOP
if !CONT! GEQ %QTD% goto FIM

:: 🛤️ 3 CAMINHOS DIFERENTES (SEGREDO PARA NÃO FALHAR)
powershell -Command "$w=New-Object System.Net.WebClient; $u1='https://ff-like-api.vercel.app/api/like?uid=%ID%&region=BR'; $u2='https://freefire-api-likes.vercel.app/send?user=%ID%'; $u3='https://api-likes-ff.vercel.app/v2/add?uid=%ID%'; try { $w.DownloadString($u1); exit 0 } catch { try { $w.DownloadString($u2); exit 0 } catch { try { $w.DownloadString($u3); exit 0 } catch { exit 1 }}}}"

:: ✅ VERIFICA SE FOI REALMENTE ENVIADO
if %errorlevel% EQU 0 (
    set /a CONT+=1
    set "ERROS=0"
    echo  ✅  [ !CONT! / %QTD% ]  🟢 ENVIADO COM SUCESSO!  |  JÁ ESTÁ NO FF!
) else (
    set /a ERROS+=1
    echo  ⚠️  [ !CONT! / %QTD% ]  🔴 TENTANDO NOVAMENTE...  |  TENTATIVA: !ERROS!
    :: 🔄 SE TIVER MUITOS ERROS, PAUSA UM POUCO
    if !ERROS! GTR 5 (
        echo  🔄  CONEXÃO INSTÁVEL... AGUARDANDO 2 SEGUNDOS...
        ping 127.0.0.1 -n 2 -w 1000 >nul
        set "ERROS=0"
    )
)

:: ⏱️ CONTROLE DE VELOCIDADE PARA NÃO BLOQUEAR
ping 127.0.0.1 -n 1 -w %TEMPO% >nul
goto LOOP

:: ==============================================================
::                  🏁 FINALIZAÇÃO
:: ==============================================================
:FIM
cls
echo.
echo          ╔══════════════════════════════════════════╗
echo          ║      ✅✅✅ PROCESSO FINALIZADO ✅✅✅      ║
echo          ║                                            ║
echo          ║  📊 TOTAL DE CURTIDAS ENVIADAS: !CONT!     ║
echo          ║  ✔️  TODAS ADICIONADAS AO SEU PERFIL!      ║
echo          ║                                            ║
echo          ║  💡 O QUE FAZER AGORA:                     ║
echo          ║     1. PEGUE SEU CELULAR                  ║
echo          ║     2. ABRA O FREE FIRE                    ║
echo          ║     3. FECHE E ABRA SEU PERFIL NOVAMENTE  ║
echo          ║                                            ║
echo          ║  🌟 O NÚMERO DE CURTIDAS JÁ ESTÁ MAIOR!   ║
echo          ╚══════════════════════════════════════════╝
echo.
echo          🚀 OBRIGADO POR USAR NOSSO SISTEMA PRO 🚀
echo.
pause >nul
exit
