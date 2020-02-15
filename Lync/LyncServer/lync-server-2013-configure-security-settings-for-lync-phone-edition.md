---
title: 'Lync Server 2013: configurar las opciones de seguridad para Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fad5a47f8b56bd97386dcab49aef9671c6f99e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Configurar las opciones de seguridad de Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Ayude a mejorar la seguridad de los dispositivos que ejecutan Lync Phone Edition a través de la configuración de seguridad SIP y las opciones de bloqueo de teléfono.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Para establecer la configuración de seguridad de Lync Phone Edition

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de dispositivo**.

4.  En la página **Configuración de dispositivo**, en la lista de configuraciones de dispositivos, haga doble clic en la configuración en la que desea cambiar los parámetros de seguridad.

5.  En **Editar configuración de dispositivo**, en **Seguridad SIP**, especifique el nivel de seguridad SIP. El nivel predeterminado, que recomendamos utilizar, es **Alto**.

6.  En **Editar configuración de dispositivo**, en **Bloqueo del teléfono**, active o desactive la casilla **Forzar bloqueo del dispositivo** (activada de forma predeterminada) y especifique la longitud mínima del PIN (6 caracteres de forma predeterminada) y el tiempo de espera (10 minutos de forma predeterminada). Recomendamos que se utilicen los valores predeterminados o bien que se incremente la longitud del PIN y se disminuya el tiempo de espera.
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información, consulte <A href="lync-server-2013-enforce-phone-locking.md">forzar el bloqueo del teléfono en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Configuración de las opciones de seguridad para teléfonos con Lync Phone Edition mediante cmdlets de Windows PowerShell

La configuración de seguridad se puede administrar mediante el shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-modify-the-sip-security-mode"></a>Para modificar el modo de seguridad SIP

  - Este comando establece como Medio el modo SIPSecurityMode para la colección global de ajustes de los teléfonos para UC. El nivel de seguridad SIP también se puede definir como Bajo o Alto (valor predeterminado).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Para modificar la longitud mínima del PIN

  - En este ejemplo, se modifican todos los ajustes de los teléfonos para UC de modo que se establece la longitud mínima del PIN en 7 dígitos.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Para obtener más información, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de la autenticación de Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

