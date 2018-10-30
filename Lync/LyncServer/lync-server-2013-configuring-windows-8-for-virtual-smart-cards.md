---
title: Configuración de Windows 8 para tarjetas inteligentes virtuales
TOCTitle: Configuración de Windows 8 para tarjetas inteligentes virtuales
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308564(v=OCS.15)
ms:contentKeyID: 56271279
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Windows 8 para tarjetas inteligentes virtuales

 

_**Última modificación del tema:** 2016-12-08_

Un factor que se debe considerar al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación. Windows 8 proporciona varias funciones de seguridad nuevas y una de las características nuevas más interesantes es la compatibilidad con tarjetas inteligentes virtuales.

Para los equipos que vienen con el chip del Módulo de plataforma segura (TPM) que cumple la especificación versión 1.2, las organizaciones ahora pueden obtener beneficios del inicio de sesión con tarjeta inteligente sin hacer inversiones adicionales en hardware. Para obtener más información, consulte el tema acerca del uso de tarjetas inteligentes virtuales con Windows 8 en [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).

## Para configurar Windows 8 para las tarjetas inteligentes virtuales

1.  Inicie sesión en el equipo con Windows 8 mediante las credenciales de un usuario habilitado en Lync.

2.  En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.

3.  Seleccione la opción **Buscar** y, a continuación, busque **Símbolo del sistema**.

4.  Haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, seleccione **Ejecutar como administrador**.

5.  Abra la consola de administración del Módulo de plataforma segura (TPM) ejecutando el siguiente comando:
    
        Tpm.msc

6.  Desde la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea al menos 1.2
    

    > [!NOTE]
    > Si recibe un diálogo que indique que no se encuentra un Módulo de plataforma segura (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el sistema BIOS.



7.  Cierre la consola de administración de TPM

8.  Desde el símbolo del sistema, cree una nueva tarjeta inteligente virtual mediante el siguiente comando:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    

    > [!NOTE]
    > Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use en su lugar la solicitud de PIN.



9.  Desde el símbolo del sistema, abra la consola de administración del equipo ejecutando el siguiente comando:
    
        CompMgmt.msc

10. En la consola de administración del equipo, seleccione **Administración de dispositivos**.

11. Expanda **Lectores de tarjetas inteligentes**.

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

