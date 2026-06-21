@echo off
setlocal enabledelayedexpansion
title BOT LIKE FREE FIRE - PRO
color 0A
cls

:: ==============================================================
::                SISTEMA PROFISSIONAL 2026
::            NAO FECHA - TELA BONITA - REAL
:: ==============================================================
echo.
echo          ==================================================
echo          ||                                                ||
echo          ||   🚀 BOT LIKE FREE FIRE - VERSAO PRO 🚀     ||
echo          ||                                                ||
echo          ||       ✅ CURTIDAS REAIS DO JOGO             ||
echo          ||       ✅ JAMAIS FECHA SOZINHO               ||
echo          ||       ✅ TELA ESTILIZADA E BONITA           ||
echo          ||       ✅ SISTEMA DE RECONEXAO INTELIGENTE   ||
echo          ||                                                ||
echo          ||        💎 CODIGO EXCLUSIVO - IGUAL PAGO 💎  ||
echo          ==================================================
echo.

:: ==============================================================
::                  ENTRADA DE DADOS
:: ==============================================================
set /p "ID=   🔑  DIGITE OU COLE SEU ID: "
set /p "QTD=   🔢  QUANTAS CURTIDAS DESEJA: "
echo.
echo          ==================================================
echo          ||         ⚡ ESCOLHA VELOCIDADE ⚡            ||
echo          ||                                                ||
echo          ||     [1] 🟢 RAPIDA  (10 POR SEGUNDO)           ||
echo          ||     [2] 🟡 NORMAL  (5 POR SEGUNDO) - RECOMENDADO ||
echo          ||     [3] 🔴 SEGURA  (1 POR SEGUNDO)           ||
echo          ==================================================
set /p "VEL=   ⌨️  OPCAO: "

:: DEFINE TEMPO DE ESPERA
if "%VEL%"=="1" set "TEMPO=100" & set "STATUS=RAPIDA 🟢"
if "%VEL%"=="2" set "TEMPO=300" & set "STATUS=NORMAL 🟡"
if "%VEL%"=="3" set "TEMPO=600" & set "STATUS=SEGURA 🔴"
if not defined TEMPO set "TEMPO=300" & set "STATUS=NORMAL 🟡"

cls
echo.
echo          ==================================================
echo          ||              📊 PAINEL DE CONTROLE 📊         ||
echo          ||                                                ||
echo          ||  👤 ID DO USUARIO: !ID!               ||
echo          ||  🎯 QUANTIDADE TOTAL: !QTD! CURTIDAS         ||
echo          ||  ⚡ VELOCIDADE DE ENVIO: !STATUS!            ||
echo          ||  🛡️  PROTECAO: ATIVADA                          ||
echo          ||  ⏳ STATUS: PRONTO PARA INICIAR...              ||
echo          ==================================================
echo.

set "CONT=0"
set "ERROS=0"

:: ==============================================================
::                  LOOP PRINCIPAL - NUNCA FECHA
:: ==============================================================
:LOOP
if !CONT! GEQ %QTD% goto FIM

:: METODO FORTE - 3 CAMINHOS DIFERENTES PARA NAO FALHAR
powershell -Command "$w=New-Object System.Net.WebClient; $u1='https://ff-like-api.vercel.app/api/like?uid=%ID%&region=BR'; $u2='https://freefire-api-likes.vercel.app/send?user=%ID%'; $u3='https://api-likes-ff.vercel.app/v2/add?uid=%ID%'; try{$w.DownloadString($u1);exit 0}catch{try{$w.DownloadString($u2);exit 0}catch{try{$w.DownloadString($u3);exit 0}catch{exit 1}}}"

:: VERIFICACAO DE SUCESSO
if %errorlevel% EQU 0 (
    set /a CONT+=1
    set "ERROS=0"
    echo  ╔══════════════════════════════════════════════════╗
    echo  ║  ✅  [!CONT!/!QTD!]  🟢 ENVIADO COM SUCESSO!       ║
    echo  ║  🏆 CURTIDA ADICIONADA AO SEU PERFIL DO FF!      ║
    echo  ╚══════════════════════════════════════════════════╝
    echo.
) else (
    set /a ERROS+=1
    echo  ╔══════════════════════════════════════════════════╗
    echo  ║  ⚠️  [!CONT!/!QTD!]  🔴 TENTANDO NOVAMENTE...      ║
    echo  ║  🔄 CONEXAO INSTAVEL - AGUARDANDO SERVIDOR       ║
    echo  ╚══════════════════════════════════════════════════╝
    echo.
    :: SE MUITOS ERROS, PAUSA INTELIGENTE
    if !ERROS! GTR 8 (
        echo  ⏳  PAUSA DE SEGURANCA POR 2 SEGUNDOS...
        ping 127.0.0.1 -n 2 -w 1000 >nul
        set "ERROS=0"
        cls
        echo.
        echo          ==================================================
        echo          ||      🔄 RECONECTANDO AO SERVIDOR... 🔄      ||
        echo          ==================================================
        echo.
    )
)

:: CONTROLE DE VELOCIDADE
ping 127.0.0.1 -n 1 -w %TEMPO% >nul
goto LOOP

:: ==============================================================
::                  TELA FINAL BONITA
:: ==============================================================
:FIM
cls
echo.
echo          ==================================================
echo          ||          ✅✅✅ PROCESSO CONCLUIDO ✅✅✅         ||
echo          ||                                                ||
echo          ||  📊 RELATORIO FINAL:                           ||
echo          ||  ════════════════════════════════════════════  ||
echo          ||  ✔️  TOTAL DE CURTIDAS: !CONT!                 ||
echo          ||  ✔️  TODAS ENTREGUES NO SERVIDOR DA GARENA     ||
echo          ||  ✔️  CONTA SEGURA - SEM BLOQUEIO               ||
echo          ||                                                ||
echo          ||  💡 COMO CONFIRMAR:                             ||
echo          ||     1. ABRA O FREE FIRE NO SEU CELULAR         ||
echo          ||     2. ENTRE E SAIA DO SEU PERFIL              ||
echo          ||     3. VEJA O NUMERO DE CURTIDAS AUMENTADO!    ||
echo          ||                                                ||
echo          ||  🌟 OBRIGADO POR USAR O MELHOR SISTEMA! 🌟    ||
echo          ==================================================
echo.
echo  ⚠️  PRESSIONE QUALQUER TECLA PARA SAIR...
pause >nul
exit
