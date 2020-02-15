---
title: 'Lync Server 2013: configuración de la entidad de certificación empresarial para la autenticación de tarjetas inteligentes'
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
ms.openlocfilehash: a49fb76019fbb3bc3356fed5de7a67b0e3a10350
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configuración de la entidad de certificación empresarial para la autenticación de tarjetas inteligentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

En la siguiente sección se describe cómo configurar una entidad de certificación (CA) raíz de empresa para que admita la autenticación de tarjeta inteligente. Para obtener información sobre cómo instalar una entidad de certificación raíz de empresa, consulte install a Enterprise root [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)Certification Authority en.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configuración de una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente

Los pasos siguientes describen cómo configurar una CA raíz de empresa para admitir la autenticación de tarjeta inteligente:

1.  Inicie sesión en el equipo de la entidad de certificación empresarial con una cuenta de administrador de dominio.

2.  Inicie el administrador del sistema y compruebe que está instalado el rol de inscripción Web de la entidad de certificación.

3.  En el menú **herramientas administrativas** , abra la consola de administración de la **entidad de certificación** .

4.  En el panel de navegación, expanda **entidad de certificación**.

5.  Haga clic con el botón secundario en **plantillas de certificado**, seleccione **nuevo**y, a continuación, seleccione **plantilla de certificado para emitir**.

6.  Seleccione **agente de inscripción**, **usuario de tarjeta inteligente**e **Inicio de sesión de tarjeta inteligente**.

7.  Haga clic en **Aceptar**.

8.  Haga clic con el botón secundario en **plantillas de certificado**.

9.  Seleccione **administrar**.

10. Abra las propiedades de la plantilla usuario de tarjeta inteligente.

11. Haga clic en la pestaña **seguridad** .

12. Cambie los permisos de la siguiente manera:
    
      - Agregar cuentas de AD de usuario individuales con permisos de lectura/inscripción (permitir), o
    
      - Agregue un grupo de seguridad que contenga usuarios de tarjetas inteligentes con permisos de lectura/inscripción (permitir), o
    
      - Adición del grupo de usuarios de dominio con permisos de lectura e inscripción (permitir)

</div>

</div>

<span> </span>

</div>

</div>

</div>

