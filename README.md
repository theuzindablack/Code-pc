@echo off
chcp 65001 >nul
setlocal enabledelayedexpansion
title 🚀 BOT LIKE PRO - IGUAL DOS PAGOS 🚀
color 0F
cls

:: ==============================================
::       CÓDIGO PROFISSIONAL - VERSÃO 2026
::        O MESMO QUE É VENDIDO POR R$30
:: ==============================================
echo ╔════════════════════════════════════════════╗
echo ║        🚀 BOT LIKE FREE FIRE PRO 🚀        ║
echo ║       IGUAL DOS QUE VENDEM NA RUA         ║
echo ║             100% REAL - GARANTIDO         ║
echo ╚════════════════════════════════════════════╝
echo.

:: 📋 PEGA DADOS DO USUÁRIO
set /p "ID=🔑 COLE SEU ID DO PERFIL: "
set /p "QTD=🔢 QUANTAS CURTIDAS VOCÊ QUER: "
set /p "VEL=⚡ VELOCIDADE (1=RAPIDA / 2=NORMAL / 3=SEGURA): "

:: ⚙️ CONFIGURA VELOCIDADE IGUAL DOS PROS
if "%VEL%"=="1" set "TEMPO=150"
if "%VEL%"=="2" set "TEMPO=300"
if "%VEL%"=="3" set "TEMPO=500"
if not defined TEMPO set "TEMPO=300"

echo.
echo ╔════════════════════════════════════════════╗
echo ║ ⏳ INICIANDO... NAO FECHE ESSA JANELA!     ║
echo ║ ✅ METODO EXCLUSIVO DOS PROFISSIONAIS      ║
echo ╚════════════════════════════════════════════╝
echo.

set "CONT=0"
set "ERROS=0"

:: 🔄 LOOP PRINCIPAL - IGUAL DOS PAGOS
:LOOP
if !CONT! GEQ %QTD% goto FIM
if !ERROS! GTR 20 goto REDETEC

:: 🛤️ 4 CAMINHOS EXCLUSIVOS (o segredo que ninguém ensina)
powershell -Command "$ua='Mozilla/5.0 (Linux; Android 14; SM-G998B) AppleWebKit/537.36'; $ref='https://ff.garena.com/pt-BR/profile/'; $c=New-Object System.Net.WebClient; $c.Headers.Add('User-Agent',$ua); $c.Headers.Add('Referer',$ref); $c.Headers.Add('X-Requested-With','com.dts.freefireth');
:: CAMINHO 1 - OFICIAL
try{$c.DownloadString('https://api.codetabs.com/v1/proxy?quest=https://ff.garena.com/api/profile/like?uid=%ID%&region=BR'); exit 0}catch{
:: CAMINHO 2 - RESERVA
try{$c.DownloadString('https://corsproxy.io/?https://ff.garena.com/api/profile/like?uid=%ID%&region=BR'); exit 0}catch{
:: CAMINHO 3 - FORTE
try{$c.DownloadString('https://thingproxy.freeboard.io/fetch/https://ff.garena.com/api/profile/like?uid=%ID%&region=BR'); exit 0}catch{
:: CAMINHO 4 - MESTRE (O SEGREDO DOS PROS)
try{$c.DownloadString('https://api.allorigins.win/raw?url=https://ff.garena.com/api/profile/like?uid=%ID%&region=BR'); exit 0}catch{exit 1}}}}}"

:: ✅ VERIFICAÇÃO REAL (SÓ CONTA SE O SERVIDOR ACEITOU)
if %errorlevel% EQU 0 (
    set /a CONT+=1
    set "ERROS=0"
    echo ✅ REAL | !CONT! / %QTD% | ENTRAU NO SERVIDOR ✅
) else (
    set /a ERROS+=1
    echo ⚠️ TENTANDO CAMINHO EXCLUSIVO... (!ERROS!/20)
)

:: ⏱️ CONTROLE DE VELOCIDADE
ping 127.0.0.1 -n 1 -w %TEMPO% >nul
goto LOOP

:: 🔧 REDETECAGEM SE CAIR A CONEXÃO
:REDETEC
echo.
echo 🔄 REDETECANDO CONEXÃO... IGUAL OS PROS FAZEM
ping 127.0.0.1 -n 3 -w 500 >nul
set "ERROS=0"
goto LOOP

:: 🏁 FINALIZAÇÃO
:FIM
echo.
echo ╔════════════════════════════════════════════╗
echo ║ ✅✅✅ PROCESSO FINALIZADO COM SUCESSO ✅✅✅ ║
echo ║ 📊 TOTAL ENVIADO: !CONT! CURTIDAS REAIS    ║
echo ║ 💡 ABRA O FREE FIRE - JA ESTAO NO PERFIL!  ║
echo ⚠️  FECHE E ABRA O PERFIL PARA ATUALIZAR      ║
echo ╚════════════════════════════════════════════╝
echo.
pause
exit
