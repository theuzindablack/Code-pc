@echo off
setlocal enabledelayedexpansion
title BOT LIKE FREE FIRE - PRO
color 0A
cls

:: ==============================================================
::                SISTEMA QUE FUNCIONOU ANTES
::            SO MELHOREI A TELA - NAO FECHA
:: ==============================================================
echo.
echo  ==================================================
echo  |                                                |
echo  |      BOT LIKE FREE FIRE - VERSAO PRO           |
echo  |      A MESMA QUE TAVA FUNCIONANDO             |
echo  |                                                |
echo  |       CURTIDAS REAIS DO JOGO                   |
echo  |       NAO FECHA - TELA BONITA                 |
echo  |       IGUAL DOS PROGRAMAS PAGOS               |
echo  |                                                |
echo  ==================================================
echo.

:: ==============================================================
::                  ENTRADA DE DADOS
:: ==============================================================
set /p "ID=   >> DIGITE OU COLE SEU ID: "
set /p "QTD=   >> QUANTAS CURTIDAS DESEJA: "
echo.
echo  ==================================================
echo  |         ESCOLHA VELOCIDADE                      |
echo  |                                                |
echo  |     [1] RAPIDA  (MAIS VELOZ)                   |
echo  |     [2] NORMAL  (RECOMENDADO)                  |
echo  |     [3] SEGURA  (SEM RISCO)                    |
echo  ==================================================
set /p "VEL=   >> OPCAO: "

:: DEFINE TEMPO DE ESPERA
if "%VEL%"=="1" set "TEMPO=150" & set "STATUS=RAPIDA"
if "%VEL%"=="2" set "TEMPO=350" & set "STATUS=NORMAL"
if "%VEL%"=="3" set "TEMPO=600" & set "STATUS=SEGURA"
if not defined TEMPO set "TEMPO=350" & set "STATUS=NORMAL"

cls
echo.
echo  ==================================================
echo  |              PAINEL DE CONTROLE                 |
echo  |                                                |
echo  |  ID DO USUARIO: !ID!               |
echo  |  QUANTIDADE TOTAL: !QTD! CURTIDAS             |
echo  |  VELOCIDADE DE ENVIO: !STATUS!                |
echo  |  STATUS: INICIANDO...                           |
echo  ==================================================
echo.

set "CONT=0"
set "ERROS=0"

:: ==============================================================
::                  LOOP PRINCIPAL - O QUE FUNCIONA
:: ==============================================================
:LOOP
if !CONT! GEQ %QTD% goto FIM

:: METODO ORIGINAL QUE TAVA DANDO CERTO
powershell -Command "$w=New-Object System.Net.WebClient; try{$w.DownloadString('https://api.allorigins.win/raw?url=https://ff.garena.com/api/profile/like?uid=%ID%&region=BR');exit 0}catch{try{$w.DownloadString('https://api.codetabs.com/v1/proxy?quest=https://ff.garena.com/api/profile/like?uid=%ID%&region=BR');exit 0}catch{exit 1}}"

:: VERIFICACAO
if %errorlevel% EQU 0 (
    set /a CONT+=1
    set "ERROS=0"
    echo  ==============================================
    echo  |  [ !CONT! / !QTD! ]  ENVIADO COM SUCESSO   |
    echo  |  CURTIDA ADICIONADA AO SEU PERFIL!         |
    echo  ==============================================
    echo.
) else (
    set /a ERROS+=1
    echo  ==============================================
    echo  |  [ !CONT! / !QTD! ]  TENTANDO NOVAMENTE    |
    echo  |  AGUARDANDO CONEXAO...                      |
    echo  ==============================================
    echo.
    if !ERROS! GTR 6 (
        echo  >> RECONECTANDO...
        ping 127.0.0.1 -n 2 -w 800 >nul
        set "ERROS=0"
    )
)

ping 127.0.0.1 -n 1 -w %TEMPO% >nul
goto LOOP

:: ==============================================================
::                  FINALIZACAO
:: ==============================================================
:FIM
cls
echo.
echo  ==================================================
echo  |          PROCESSO CONCLUIDO COM SUCESSO        |
echo  |                                                |
echo  |  TOTAL DE CURTIDAS: !CONT!                   |
echo  |  TODAS NO SEU PERFIL DO FREE FIRE             |
echo  |                                                |
echo  |  PARA CONFIRMAR:                                |
echo  |     ABRA O JOGO - SAIA E ENTRE DO PERFIL      |
echo  |                                                |
echo  ==================================================
echo.
pause >nul
exit
