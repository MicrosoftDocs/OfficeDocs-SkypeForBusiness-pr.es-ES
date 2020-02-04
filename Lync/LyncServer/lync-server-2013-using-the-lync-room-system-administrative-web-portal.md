---
title: 'Lync Server 2013: Usar el portal web administrativo de Lync Room System'
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
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Usar el portal web administrativo de Lync Room System en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-10_

Después de implementar LRS en el servidor, puede comprobar el estado de todas las salas de LRS iniciando sesión en el portal web administrativo de LRS desde un explorador.

<div>

## <a name="sign-in"></a>Iniciar sesión

1.  Vaya a la siguiente dirección URL:
    
    https://\<fe: servidor\>/LRS

2.  Escriba las credenciales de la cuenta LRSSupport o una cuenta que se haya agregado al grupo de seguridad LRSSupportAdminGroup.

![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión en el portal de administración del sistema Lync Room")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Página de resumen del portal web administrativo LRS

La página de Resumen proporciona la siguiente información para todas las salas de LRS implementadas en el servidor:

  - **Etiquete**   el nombre personalizado que el administrador da al salón. Para establecer la etiqueta en el portal, haga clic en el nombre de la sala.

  - **Salud**   el estado de mantenimiento de la sala, derivado del estado de mantenimiento acumulado de la sala, que se muestra en la sección estado de la página Configuración de la sala.

  - **Siguiente reunión**   la fecha y la hora en la que se programó la próxima reunión.

  - **Versión LRS, fabricante, modelo**   estos valores están preestablecidos en LRS. Según el fabricante, estos campos pueden dejarse en blanco.

  - **Última actualización**   : muestra la última vez que se actualizó la Página Web.

![Vista resumida del portal de administración del sistema Lync Room](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Vista resumida del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="lrs-room-information"></a>Información de la sala LRS

La sección información de la sala del portal le permite ver y configurar salas LRS individuales. Contiene cuatro secciones: configuración, detalles, solución de problemas y estado.

<div>

## <a name="settings"></a>Configuración

En la sección de configuración, puede establecer la contraseña, la etiqueta de la sala y los valores de volumen predeterminados de la sala. Si estableces esta configuración, los cambios solo se replicarán después de reiniciar la consola LRS. Solo verá la configuración de actualizaciones del sistema para los sistemas de salas de Lync que sean de la versión 15,12 y posteriores.

![Configuración de salones del portal de administración del sistema Lync Room](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configuración de salones del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="details"></a>Detalles

En la sección de detalles se proporciona un resumen de solo lectura de la configuración de la sala de LRS, que incluye la hora de la última actualización; reunión siguiente; últimas actualizaciones, mantenimiento y calibración; configuración predeterminada de timbre, micrófono y altavoz; versión URI DEL SIP; número de pantallas y detalles de cada pantalla; Estado y actividad.

![Vista en detalle del portal de administración del sistema Lync Room](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Vista en detalle del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="troubleshooting"></a>Solución de problemas

La sección de solución de problemas se puede usar para recopilar remotamente registros y guardarlos en una ubicación especificada. También puede reiniciar la consola LRS (interfaz de usuario de LRS) o reiniciar todo el sistema. Para recopilar registros, proporcione una ruta de acceso a la carpeta en el formato especificado y asegúrese de que la carpeta tiene permisos de escritura otorgados a la cuenta de la máquina LRS. Si el tamaño de los registros es muy grande, la recopilación de registros puede tardar hasta 5 minutos. Actualice la página para ver el estado actualizado.

![Registro de salones del portal de administración del sistema Lync Room](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registro de salones del portal de administración del sistema Lync Room")

</div>

<div>

## <a name="health"></a>Mantenimiento

La sección estado ofrece una indicación visual del estado de la conexión de Lync Server, dispositivo de audio, dispositivo de vídeo, estado de resistencia y dispositivo de pantalla.

![Estado de los salones del portal de administración del sistema Lync Room](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Estado de los salones del portal de administración del sistema Lync Room")

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
> <P>Si la contraseña de la cuenta LRSApp expira, no podrá ver el estado de las salas. Configure la contraseña de la cuenta LRSAppuser para que nunca expire, o asegúrese de actualizar la contraseña cuando esté cerca de la fecha de expiración.</P>
> <LI>
> <P>El portal web administrativo de LRS solo se admite para las implementaciones locales.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>¿Por qué no puedo iniciar sesión en el portal web administrativo?

  - Al abrir https://localhost/lrs, podrá ver la página de inicio de sesión pero, cuando escriba sus credenciales, no podrá iniciar sesión. En este caso, debe abrir https://FQDNofFEserver/lrs para iniciar sesión en el portal web administrativo.

  - Si el equipo desde el que tiene acceso al portal web administrativo está en un grupo de trabajo, "http://" no funcionará. Usa "https" en su lugar.

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver LRS en el portal web administrativo?

  - Asegúrese de tener cuentas LRS en la implementación y de que se hayan creado de acuerdo con las recomendaciones de implementación del portal web de LRS. Asegúrese de que las cuentas de LRS se aprovisionan mediante enable-CsMeetingRoom, not enable-CsUser, en el servidor de Lync.

  - Si ha creado cuentas LRS y no puede ver las cuentas en el portal web administrativo, recopile los registros de servidor con la herramienta de registro de Lync Server con el componente **MeetingPortal** seleccionado y, a continuación, envíelos a su contacto de soporte de LRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver el estado de LRS en el portal web administrativo?

  - Asegúrese de que la cuenta de usuario LRSApp esté habilitada para SIP.

  - Si sigue teniendo problemas, recopile el archivo **Trace. log** en el sistema LRS de D:\\Tracing\\LRSAdminLogs\\y envíelo a su contacto de soporte de LRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

