---
title: 'Lync Server 2013: configuración del modo de privacidad de presencia mejorada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91326778777e6ddd1db2f8938cfb78e96ed8c7f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configurar el modo de privacidad de presencia mejorada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-08_

Con el modo de privacidad de presencia mejorada, los usuarios pueden restringir la información de presencia para que esté visible solo para los contactos que aparecen en la lista de contactos de Lync 2013. Los cmdlets **New-CsPrivacyConfiguration** y **set-CsPrivacyConfiguration** tienen un parámetro EnablePrivacyMode controla esta opción. Cuando EnablePrivacyMode se establece en true, la opción para restringir la información de presencia a los contactos está disponible en las opciones de estado de Lync 2013. Si EnablePrivacyMode está definido en False, los usuarios pueden elegir si quieren permitir que todo el mundo vea siempre su información de presencia o adaptarse a los posibles cambios que el administrador realice en el modo de privacidad.

<div>


> [!IMPORTANT]  
> Las versiones anteriores no respetan la configuración de privacidad de Lync 2013 y Lync 2010 (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007). Si se permite iniciar sesión en versiones anteriores de Office Communicator, una persona a la que no se le haya autorizado ver el estado, la información de contacto o la imagen del usuario de Lync 2013 puede verla. Además, la configuración de privacidad de un usuario de Lync 2013 se restablece si inicia sesión con una versión anterior de Communicator.<BR>Por estas razones, en un escenario de migración, antes de habilitar el modo de privacidad de presencia mejorada: 
> <UL>
> <LI>
> <P>Asegúrese de que todos los usuarios tienen instalado Lync 2013.</P>
> <LI>
> <P>Defina una regla de directiva de versiones de cliente para impedir que versiones anteriores de Communicator inicien sesión.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Para habilitar el modo de privacidad de presencia mejorada

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente comando:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Este comando habilita el modo de privacidad para todos los parámetros de privacidad que se encuentran actualmente en uso en la organización. Para obtener más información sobre cómo la Directiva de modo de privacidad de presencia mejorada de Lync Server administra la presencia de contactos para el cliente de Lync 2013, consulte el artículo de Microsoft Knowledge base [que habilita Lync Server Enhanced Presence el modo de privacidad actualiza el estado de presencia de algunos contactos de Lync a "no disponible"](https://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

