---
title: 'Lync Server 2013: configuración de las opciones predeterminadas de imagen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24d32ca52df9c75cf2a0816ff81bd5eaa775d22a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Configuración de las opciones predeterminadas de imagen en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-22_

De forma predeterminada, las imágenes de los usuarios se muestran automáticamente. Si los usuarios quieren ocultar sus imágenes, pueden seleccionar la opción **ocultar mi foto** en el cliente de Lync. Sin embargo, otras aplicaciones de Office omiten esta configuración.

Si la posibilidad de mostrar imágenes incluso cuando el usuario está desactivado es un problema, puede cambiar la configuración de presentación de imágenes de Lync de forma global o para un sitio o servicio, de modo que las imágenes de los usuarios no se muestren de forma predeterminada. Use el siguiente cmdlet de Shell de administración de Lync Server para que no se muestren las imágenes del usuario a menos que seleccionen explícitamente la opción **Mostrar mi foto** en el cliente:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Para obtener más información acerca de este cmdlet, consulte [set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) en la documentación del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

