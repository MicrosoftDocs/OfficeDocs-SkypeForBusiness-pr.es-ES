---
title: 'Lync Server 2013: configuración de Windows 8 para tarjetas inteligentes virtuales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8fe9fb9bcca80e7e84f19bdc484dc693b1ee68
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configurar Windows 8 para usar tarjetas inteligentes virtuales con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

Un factor a tener en cuenta al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación. Windows 8 proporciona una serie de nuevas capacidades de seguridad y una de las características nuevas más interesantes es la compatibilidad con tarjetas inteligentes virtuales.

Para los equipos que disponen de un chip de módulo de plataforma segura (TPM) que cumple la versión 1,2 de la especificación, las organizaciones ahora pueden obtener las ventajas del inicio de sesión con tarjeta inteligente sin necesidad de realizar ninguna inversión adicional en el hardware. Para obtener más información, consulte uso de tarjetas inteligentes virtuales con Windows [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)8 en.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para tarjetas inteligentes virtuales

1.  Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Lync.

2.  En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.

3.  Seleccione la opción de **búsqueda** y, a continuación, busque el **símbolo del sistema**.

4.  Haga clic con el botón secundario en **símbolo del sistema**y seleccione **Ejecutar como administrador**.

5.  Abra la consola de administración del módulo de plataforma segura (TPM) ejecutando el siguiente comando:
    
        Tpm.msc

6.  En la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea como mínimo de 1,2
    
    <div>
    

    > [!NOTE]  
    > Si recibe un cuadro de diálogo que indica que no se encuentra un módulo de plataforma de confianza (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el BIOS del sistema.

    
    </div>

7.  Cerrar la consola de administración de TPM

8.  Desde el símbolo del sistema, cree una nueva tarjeta inteligente virtual con el siguiente comando:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use/PIN prompt en su lugar.

    
    </div>

9.  Desde el símbolo del sistema, abra la consola de administración de equipos ejecutando el siguiente comando:
    
        CompMgmt.msc

10. En la consola de administración de equipos, seleccione **Administración de dispositivos**.

11. Expanda **lectores de tarjetas inteligentes**.

12. Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

