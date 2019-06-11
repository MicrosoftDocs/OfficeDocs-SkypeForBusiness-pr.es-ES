---
title: 'Lync Server 2013: configuración de Windows 8 para tarjetas inteligentes virtuales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configuración de Windows 8 para el uso de tarjetas inteligentes virtuales con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

Un factor que se necesita considerar al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación. Windows 8 proporciona una serie de nuevas capacidades de seguridad y una de las características nuevas más interesantes es la compatibilidad con las tarjetas inteligentes virtuales.

Para los equipos que vienen con el chip del Módulo de plataforma segura (TPM) que cumple la especificación versión 1.2, las organizaciones ahora pueden obtener beneficios del inicio de sesión con tarjeta inteligente sin hacer inversiones adicionales en hardware. Para obtener más información, consulte uso de tarjetas inteligentes virtuales con Windows [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)8 en.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para las tarjetas inteligentes virtuales

1.  Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Lync.

2.  En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.

3.  Seleccione la opción **Buscar** y, luego, busque **Command Prompt**.

4.  Haga clic con el botón derecho en **Símbolo del sistema** y, luego, seleccione **Ejecutar como administrador**.

5.  Abra la consola de administración del Módulo de plataforma segura (TPM) ejecutando el siguiente comando:
    
        Tpm.msc

6.  Desde la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea al menos 1.2
    
    <div>
    

    > [!NOTE]  
    > Si recibe un diálogo que indique que no se encuentra un Módulo de plataforma segura (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el sistema BIOS.

    
    </div>

7.  Cierre la consola de administración de TPM

8.  Desde el símbolo del sistema, cree una tarjeta inteligente virtual por medio del siguiente comando:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use en su lugar la solicitud de PIN.

    
    </div>

9.  Desde el símbolo del sistema, abra la consola de administración del equipo ejecutando el siguiente comando:
    
        CompMgmt.msc

10. En la consola de administración del equipo, seleccione **Administración de dispositivos**.

11. Expanda **Lectores de tarjetas inteligentes**.

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

