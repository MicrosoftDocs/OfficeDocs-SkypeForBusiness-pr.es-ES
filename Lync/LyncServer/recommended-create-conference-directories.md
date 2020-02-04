---
title: (Recomendado) Crear directorios de conferencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d525951dcb77ee365c9c83461f678c26ae53af6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a>(Recomendado) Crear directorios de conferencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-03_

Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia al usar Lync 2013 y el identificador de conferencia de acceso telefónico local que usa un participante de conferencia de acceso telefónico local para unirse a la Conferencia. El formato del identificador de conferencia es el siguiente:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Con esta pauta, los identificadores de conferencia generalmente se mantienen reducidos. Sin embargo, cuando el número de directorios de conferencia (en los grupos) exceda de 9, la longitud del id. de conferencia aumentará para dar soporte a otras conferencias.

<div>

## <a name="creating-a-conference-directory"></a>Crear un directorio de conferencia

1.  En el shell de administración de Lync Server, escriba el siguiente cmdlet:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    Por ejemplo, el siguiente ejemplo crea un directorio de conferencia con la identidad 42, hospedada en el grupo atl-cs-001.litwareinc.com:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

