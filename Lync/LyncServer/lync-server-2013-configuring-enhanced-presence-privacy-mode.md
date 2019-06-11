---
title: 'Lync Server 2013: configuración del modo de privacidad de presencia mejorada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configuración del modo de privacidad de presencia mejorada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-08_

Con el modo de privacidad de presencia mejorado, los usuarios pueden restringir la información de presencia para que solo esté visible para los contactos que aparecen en la lista de contactos de Lync 2013. Los cmdlets **New-CsPrivacyConfiguration** y **set-CsPrivacyConfiguration** tienen un parámetro EnablePrivacyMode controle esta opción. Cuando EnablePrivacyMode se establece en true, la opción para restringir la información de presencia a los contactos está disponible en las opciones de estado de Lync 2013. Cuando EnablePrivacyMode se establece en false, los usuarios pueden elegir permitir que todos vean la información de presencia o adherirse a los cambios futuros que realice el administrador en el modo de privacidad.

<div>


> [!IMPORTANT]  
> Las configuraciones de privacidad de Lync 2013 y Lync 2010 no se admiten en versiones anteriores (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007). Si se permite que las versiones anteriores de Office Communicator puedan iniciar sesión, alguien que no haya recibido autorización puede ver el estado, la información de contacto o la imagen de un usuario de Lync 2013. Además, la configuración de privacidad de un usuario de Lync 2013 se restablece si inicia sesión con una versión anterior de Communicator.<BR>Por estos motivos, en un escenario de migración, antes de habilitar el modo de privacidad de presencia mejorado: 
> <UL>
> <LI>
> <P>Asegúrese de que todos los usuarios tienen instalado Lync 2013.</P>
> <LI>
> <P>Defina una regla de directiva de versión de cliente para evitar que versiones anteriores de Communicator inicien sesión.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Para habilitar el modo de privacidad de presencia mejorado

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente comando:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Este comando habilita el modo de privacidad para todas las opciones de configuración de privacidad actualmente en uso en la organización. Para obtener más información sobre cómo la configuración de directiva de modo de privacidad de presencia mejorada de Lync Server administra la presencia del contacto para el cliente de Lync 2013, consulte el artículo de Microsoft KB [habilitando Lync Server el modo de privacidad de presencia mejorada actualiza la presencia el estado de algunos contactos de Lync a "no disponible"](http://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[Nuevo: CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

