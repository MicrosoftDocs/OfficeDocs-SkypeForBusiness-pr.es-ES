---
title: 'Lync Server 2013: usar el portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d950bd62b2db91f60dd5828f79977472a9c5d573
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Usar el portal web administrativo del sistema Lync Room en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-10_

Después de implementar LRS en el servidor, puede comprobar el estado de todos los salones LRS iniciando sesión en el portal web administrativo de LRS desde un explorador.

<div>

## <a name="sign-in"></a>Iniciar sesión

1.  Vaya a la siguiente dirección URL:
    
    https://\<fe-servidor\>/LRS

2.  Escriba las credenciales de la cuenta LRSSupport o de una cuenta que se haya agregado al grupo de seguridad LRSSupportAdminGroup.

![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Página de resumen del portal web administrativo LRS

La página de Resumen proporciona la siguiente información para todos los salones de LRS implementados en el servidor:

  - **Etiquete**   el nombre personalizado que el administrador da al salón. La etiqueta se puede establecer en el portal haciendo clic en el nombre del salón.

  - **Mantenimiento**   el estado de mantenimiento de la sala, que se deriva del estado de mantenimiento agregado de la sala, que se muestra en la sección estado de la página Configuración de la sala.

  - **Siguiente reunión**   la fecha y hora en que se programó la próxima reunión.

  - **Versión LRS, fabricante, modelo**   estos valores están preestablecidos en LRS. Según el fabricante, estos campos podrían dejarse en blanco.

  - **Última actualización**   muestra la última vez que se actualizó la Página Web.

![Vista de resumen del portal de administración del sistema Lync Room](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Vista de resumen del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="lrs-room-information"></a>Información de salón de LRS

La sección de información de la sala del portal permite ver y configurar salones de LRS individuales. Contiene cuatro secciones: configuración, detalles, solución de problemas y mantenimiento.

<div>

## <a name="settings"></a>Configuración

En la sección configuración, puede establecer la contraseña, la etiqueta de salón y los niveles de volumen predeterminados para el salón. Si configura estas opciones, los cambios solo se replican después de reiniciar la consola LRS. Solo verá la configuración de actualizaciones del sistema para sistemas de salas de Lync que sean la versión 15,12 y posteriores.

![Configuración del salón del portal de administración del sistema de Lync Room](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configuración del salón del portal de administración del sistema de Lync Room")

</div>

<div>

## <a name="details"></a>Detalles

La sección de detalles proporciona un resumen de solo lectura de la configuración de la sala LRS, que incluye: la hora de la última actualización; próxima reunión; últimas actualizaciones, mantenimiento y calibración; configuración predeterminada de altavoces, micrófono y timbre; versi URI DE SIP; número de pantallas y detalles de cada pantalla; Estado y actividad.

![Vista detallada del portal de administración del sistema Lync Room](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Vista detallada del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="troubleshooting"></a>Solución de problemas

La sección de solución de problemas se puede usar para recopilar registros de forma remota y guardarlos en una ubicación específica. También puede reiniciar la consola LRS (interfaz de usuario LRS) o reiniciar todo el sistema. Para recopilar registros, especifique una ruta de acceso a la carpeta en el formato especificado y asegúrese de que la carpeta tiene permisos de escritura en la cuenta del equipo LRS. Si el tamaño del registro es demasiado grande, puede tardar hasta 5 minutos en finalizar la recopilación de registros. La actualización de la página le dará el estado más reciente.

![Registro del salón del portal de administración del sistema Lync Room](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registro del salón del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="health"></a>Salud

La sección estado ofrece una indicación visual del estado de la conexión de Lync Server, el dispositivo de audio, el dispositivo de vídeo, el estado de resistencia y el dispositivo de pantalla.

![Portal de administración del sistema Lync Room Health Room](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Portal de administración del sistema Lync Room Health Room")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Notas adicionales sobre el portal web administrativo

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Los cambios de configuración solo se aplican después de reiniciar el sistema LRS.</P>
> <LI>
> <P>Si la contraseña de la cuenta LRSApp expira, no podrá ver el estado de las salas. Configure la contraseña de la cuenta LRSAppuser para que nunca expire o asegúrese de actualizar la contraseña cuando esté próximo a expirar.</P>
> <LI>
> <P>El portal web administrativo LRS solo es compatible con las implementaciones locales.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>¿Por qué no puedo iniciar sesión en el portal web administrativo?

  - Al abrir https://localhost/lrs, podrás ver la página de inicio de sesión, pero, cuando escribas tus credenciales, no podrás iniciar sesión. En este caso, debe abrir https://FQDNofFEserver/lrs para iniciar sesión en el portal web administrativo.

  - Si el equipo desde el que tiene acceso al portal web administrativo se encuentra en un grupo de trabajo, "http://" no funcionará. Use "https" en su lugar.

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver LRS en el portal web administrativo?

  - Asegúrese de que tiene cuentas LRS en su implementación y que se crean de acuerdo con las recomendaciones de implementación del portal web administrativo LRS. Asegúrese de que las cuentas LRS se aprovisionan mediante enable-CsMeetingRoom, no enable-CsUser, en el servidor de Lync.

  - Si ha creado cuentas LRS y no puede ver las cuentas en el portal web administrativo, recopile los registros del servidor mediante la herramienta de registro de Lync Server con el componente **MeetingPortal** seleccionado y, a continuación, envíelos al contacto de soporte de LRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver el estado de LRS en el portal web administrativo?

  - Asegúrese de que la cuenta de usuario de LRSApp esté habilitada para SIP.

  - Si sigue teniendo problemas, recopile el archivo **Trace. log** en el sistema LRS de D:\\Tracing\\LRSAdminLogs\\y, a continuación, envíelo al contacto de soporte LRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

