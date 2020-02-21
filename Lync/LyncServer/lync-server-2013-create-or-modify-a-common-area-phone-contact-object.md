---
title: 'Lync Server 2013: crear o modificar un objeto de contacto de teléfono de área común'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d2eb58df1e5c83f23fdb1d31ba73b408d107a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Crear o modificar un objeto de contacto telefónico de área común en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Para crear objetos de contacto de servicios de dominio de Active Directory para todos los teléfonos de área común, use el cmdlet **New-CsCommonAreaPhone** . Este cmdlet puede crear nuevos objetos de contacto para su uso con teléfonos de área común o puede asociar objetos de contacto existentes con un nuevo teléfono de área común. Para modificar las propiedades de los objetos de contacto asociados con los teléfonos de área común, use el cmdlet **set-CsCommonAreaPhone** . Los parámetros opcionales para **set-CsCommonAreaPhone** permiten cambiar elementos, como el nombre para mostrar de Active Directory del contacto o el identificador uniforme de recursos (URI) de línea asociado al teléfono, y habilitar y deshabilitar la cuenta para su uso con Lync Server. Para obtener más información sobre todas las modificaciones disponibles, consulte la sección parámetros en [set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Para obtener más información sobre los parámetros **New-CsCommonAreaPhone** , vea [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Puede ejecutar estos dos cmdlets desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Creación de un objeto de contacto de teléfono de área común

  - Para crear un nuevo objeto de contacto de teléfono de área común, use el cmdlet **New-CsCommonAreaPhone** . Como mínimo, debe proporcionar la siguiente información al crear un objeto de contacto:
    
      - **LineUri**: el número de teléfono asignado al teléfono de área común. Tenga en cuenta que debe usar el formato E. 164 Cuando especifique el número de teléfono.
    
      - **RegistrarPool**: el nombre de dominio completo (FQDN) del grupo de registrador donde se hospedará el objeto de contacto.
    
      - **Ou**: nombre distintivo del contenedor de Active Directory donde se creará el objeto de contacto.
    
    También le recomendamos que proporcione un nombre para mostrar de los servicios de dominio de Active Directory. De lo contrario, tendrá que usar un GUID para especificar la identidad del teléfono. Por ejemplo:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Modificación de un objeto de contacto de teléfono de área común

  - Para modificar las propiedades de un teléfono de área común existente, el objeto de contacto use el cmdlet **set-CsCommonAreaPhone** . Por ejemplo, este comando configura la dirección SIP del teléfono de área común con DisplayName vestíbulo:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Para obtener más información, consulte los temas de ayuda del cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) y el cmdlet [set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

