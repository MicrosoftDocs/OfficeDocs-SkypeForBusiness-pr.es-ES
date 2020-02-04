---
title: 'Lync Server 2013: configuración de la CA de empresa para la autenticación de tarjetas inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44df62031e679c641b4c7dbe6b5c205e1ae899e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configuración de CA de empresa para la autenticación de tarjetas inteligentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

En la sección siguiente se describe cómo configurar una entidad de certificación (CA) raíz de empresa para admitir la autenticación de tarjetas inteligentes. Para obtener información sobre cómo instalar una entidad emisora de certificados raíz de empresa, vea instalar una [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)entidad de certificación raíz de empresa en.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar una entidad emisora de certificados raíz de empresa para admitir la autenticación de tarjetas inteligentes

En los siguientes pasos, se describe cómo configurar una CA raíz empresarial para admitir la autenticación de tarjeta inteligente:

1.  Inicie sesión en el equipo de la CA empresarial usando una cuenta de administrador de dominio.

2.  Inicie el Administrador del sistema y compruebe que está instalado el rol Inscripción web de entidad de certificación.

3.  En el menú **Herramientas administrativas**, abra la consola de administración de **Entidad de certificación**.

4.  En el panel de navegación, expanda **Entidad de certificación**.

5.  Haga clic con el botón derecho en **Plantillas de certificado**, elija **Nueva** y, luego, elija **Plantilla de certificado que se va a emitir**.

6.  Elija **Enrollment Agent**, **Usuario de tarjeta inteligente** e **Inicio de sesión de Tarjeta inteligente**.

7.  Haga clic en **Aceptar**.

8.  Haga clic con el botón derecho en **Plantillas de certificado**.

9.  Elija **Administrar**.

10. Abra las propiedades de la plantilla Usuario de tarjeta inteligente.

11. Haga clic en la pestaña **Seguridad**.

12. Cambie los permisos como se indica a continuación:
    
      - Agregue cuentas de usuario individuales de AD con los permisos Leer/Inscribir (permitir), o
    
      - Agregue un grupo de seguridad que contenga los usuarios de tarjeta inteligente con permisos Leer/Inscribir (permitir), o
    
      - Agregue el grupo Usuarios del dominio con los permisos Leer/Inscribir (permitir)

</div>

</div>

<span> </span>

</div>

</div>

</div>

