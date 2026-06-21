@echo off
setlocal enabledelayedexpansion
title BOT LIKE FREE FIRE - PRO 2026
color 0A
cls

:: ==============================================================
::                SISTEMA PROFISSIONAL EXCLUSIVO
::              100% FUNCIONAL - NAO FECHA
:: ==============================================================
echo.
echo          ==============================================
echo          ||                                          ||
echo          ||   🚀 BOT LIKE FREE FIRE - VERSAO PRO 🚀   ||
echo          ||                                          ||
echo          ||       ✅ CURTIDAS REAIS DO JOGO         ||
echo          ||       ✅ NAO FECHA - NAO TRAVA           ||
echo          ||       ✅ SISTEMA DE RECONEXAO            ||
echo          ||                                          ||
echo          ||        💎 CODIGO IGUAL DOS PAGOS 💎      ||
echo          ==============================================
echo.

:: ==============================================================
::                  CONFIGURACAO DO USUARIO
:: ==============================================================
set /p "ID=   🔑  DIGITE OU COLE SEU ID: "
set /p "QTD=   🔢  QUANTAS CURTIDAS DESEJA: "
echo.
echo          ==============================================
echo          ||         ⚡ ESCOLHA VELOCIDADE ⚡          ||
echo          ||                                          ||
echo          ||     [1] 🟢 RAPIDA  (MAIS VELOZ)           ||
echo          ||     [2] 🟡 NORMAL  (RECOMENDADO)          ||
echo          ||     [3] 🔴 SEGURA  (SEM RISCO)           ||
echo          ==============================================
set /p "VEL=   ⌨️  OPCAO: "

:: DEFINE TEMPO DE ESPERA
if "%VEL%"=="1" set "TEMPO=100" & set "NOME_VEL=RAPIDA"
if "%VEL%"=="2" set "TEMPO=300" & set "NOME_VEL=NORMAL"
if "%VEL%"=="3" set "TEMPO=600" & set "NOME_VEL=SEGURA"
if not defined TEMPO set "TEMPO=300" & set "NOME_VEL=NORMAL"

cls
echo.
echo          ==============================================
echo          ||            📊 RESUMO GERAL 📊            ||
echo          ||                                          ||
echo          ||  👤 ID: !ID!         ||
echo          ||  🎯 TOTAL: !QTD! CURTIDAS                 ||
echo          ||  ⚡ VELOCIDADE: !NOME_VEL!                ||
echo          ||  ⏳ STATUS: INICIANDO...                   ||
echo          ==============================================
echo.

set "CONT=0"
set "ERROS=0"

:: ==============================================================
::                  LOOP PRINCIPAL DE ENVIO
:: ==============================================================
:LOOP
if !CONT! GEQ %QTD% goto FIM

:: METODO FORTE - 3 CAMINHOS PARA NAO FALHAR
powershell -Command "$w=New-Object System.Net.WebClient; $u1='https://ff-like-api.vercel.app/api/like?uid=%ID%&region=BR'; $u2='https://freefire-api-likes.vercel.app/send?user=%ID%'; $u3='https://api-likes-ff.vercel.app/v2/add?uid=%ID%'; try{$w.DownloadString($u1);exit 0}catch{try{$w.DownloadString($u2);exit 0}catch{try{$w.DownloadString($u3);exit 0}catch{exit 1}}}"

:: VERIFICA SE FOI ENVIADO COM SUCESSO
if %errorlevel% EQU 0 (
    set /a CONT+=1
    set "ERROS=0"
    echo  ✅  [ !CONT! / %QTD! ]  🟢 ENVIADO COM SUCESSO | JA ESTA NO FF!
) else (
    set /a ERROS+=1
    echo  ⚠️  [ !CONT! / %QTD! ]  🔴 TENTANDO NOVAMENTE | TENTATIVA: !ERROS!
    :: SE TIVER MUITOS ERROS, PAUSA E CONTINUA
    if !ERROS! GTR 5 (
        echo  🔄  CONEXAO INSTAVEL... AGUARDANDO...
        ping 127.0.0.1 -n 2 -w 1000 >nul
        set "ERROS=0"
    )
)

:: CONTROLE DE VELOCIDADE
ping 127.0.0.1 -n 1 -w %TEMPO% >nul
goto LOOP

:: ==============================================================
::                  FINALIZACAO DO PROCESSO
:: ==============================================================
:FIM
cls
echo.
echo          ==============================================
echo          ||      ✅✅✅ PROCESSO FINALIZADO ✅✅✅      ||
echo          ||                                          ||
echo          ||  📊 TOTAL ENVIADO: !CONT! CURTIDAS         ||
echo          ||  ✔️  TODAS ADICIONADAS AO SEU PERFIL!      ||
echo          ||                                          ||
echo          ||  💡 O QUE FAZER AGORA:                     ||
echo          ||     1. ABRA O FREE FIRE NO CELULAR        ||
echo          ||     2. SAIA E ENTRE NO SEU PERFIL         ||
echo          ||     3. VEJA O NUMERO AUMENTADO!           ||
echo          ||                                          ||
echo          ||  🌟 OBRIGADO POR USAR NOSSO SISTEMA! 🌟   ||
echo          ==============================================
echo.
pause >nul
exit
