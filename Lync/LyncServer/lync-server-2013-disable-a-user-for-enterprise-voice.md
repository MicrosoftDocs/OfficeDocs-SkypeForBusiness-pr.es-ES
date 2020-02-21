---
title: 'Lync Server 2013: deshabilitar a un usuario para telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdcc6f69280357730e34f987f3c197db6950c285
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Deshabilitar a un usuario para la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Use el siguiente procedimiento para deshabilitar Enterprise Voice para una cuenta de usuario que esté habilitada para Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para deshabilitar una cuenta de usuario para telefonía IP empresarial

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee habilitar para la telefonía IP empresarial.

6.  En el menú **Editar **, haga clic en **Mostrar detalles **.

7.  En la página **Editar usuario de Lync Server **, en **Telefonía **, haga clic en cualquier opción excepto **Telefonía IP empresarial **.
    
    <div>
    

    > [!NOTE]  
    > Para impedir que un usuario realice llamadas de audio o vídeo mediante Lync, en <STRONG>telefonía</STRONG>, haga clic en <STRONG>audio y vídeo deshabilitado</STRONG>.

    
    </div>

8.  Haga clic en **Confirmar**.

El usuario ahora no puede usar la característica Enterprise Voice.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Administración de la telefonía IP empresarial para los usuarios en Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

