---
title: Publicación de Office Web Apps Server con un servidor proxy inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d1dae773c96cfa6d16994e5b3c6aec2504b16c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

Si desea que los usuarios externos (es decir, los usuarios que inicien sesión desde fuera del firewall de la organización) tengan acceso a las presentaciones de PowerPoint del servidor Office Web Apps, entonces deberá utilizar el servidor Office Web Apps y un servidor proxy inverso como Microsoft Forefront Threat Management Gateway. Esto también significa que tendrá que crear y configurar una regla de publicación de sitios web; Esta regla le ayudará a asegurarse de que los usuarios puedan conectarse al servidor. Si no necesita brindar acceso a usuarios externos, entonces no necesita configurar una regla de publicación de sitio web.

Para configurar una regla de publicación de sitios web en Forefront Threat Management Gateway, complete el siguiente procedimiento:

1.  Haga clic en **Inicio**, en **Todos los programas**, en **Microsoft Forefront TMG** y, a continuación, en**Administración de Forefront TMG**.

2.  En Forefront TMG, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En el Asistente de nueva regla de publicación web, en la página **Bienvenido al Asistente de nueva regla de publicación web**, escriba un nombre para su nueva regla en el cuadro **nombre de regla de publicación web** (por ejemplo, **Regla del servidor Office Web Apps**) y luego haga clic en **Siguiente**.

4.  En la página **Especificar acción de regla**, seleccione **Permitir** y luego haga clic en **Siguiente**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga** y, a continuación, haga clic en **Siguiente**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectarse al servidor web o conjunto de servidores publicado** y, a continuación, haga clic en **Siguiente**.

7.  En la página **Detalles internos de publicación**, escriba el FQDN de su servidor Office Web Apps (por ejemplo, **officewebapps01.contoso.com**) en el cuadro **Nombre de sitio interno** y luego haga clic en **Siguiente**. El nombre ingresado en el cuadro **Nombre de sitio interno** debe aparecer en el campo Asunto o el campo Nombre alternativo de asunto del certificado que ha asignado al servidor Office Web Apps.

8.  En la página **detalles internos de publicación** , ** / ** escriba el cuadro **ruta de acceso (opcional)** y, a continuación, haga clic en **siguiente**. La sintaxis\* /le ayudará a asegurarse de que se publiquen todas las carpetas y subcarpetas del sitio.

9.  En la página **Detalles de nombre público**, seleccione **Este nombre de dominio (escribir debajo)** de la lista desplegable **Aceptar solicitudes de** y luego escriba el nombre de dominio completo de su servidor Office Web Apps en el cuadro Nombre público. Este nombre deberá ser el nombre utilizado para acceder a su sitio web. Por ejemplo, si se obtiene acceso a su sitio con la http://officewebapps01.contoso.com dirección URL, escriba **officewebapps01.contoso.com** en el cuadro **nombre público** .

10. Haga clic en **Siguiente**.

11. En la página **Seleccionar escucha de web**, haga clic en **Nuevo**.

12. En el Asistente para nueva definición de escucha de web, escriba un nombre para la nueva escucha de web (por ejemplo, **SSL**) en el cuadro **Nombre de escucha de web** y luego haga clic en **Siguiente**.

13. En la página **Seguridad de la conexión de cliente**, seleccione **Requerir conexiones seguras SSL con los clientes** y, a continuación, haga clic en **Siguiente**.

14. En la página **Direcciones IP de escucha de web**, seleccione **Externa**, seleccione **Interna** y, a continuación, haga clic en **Siguiente**.

15. En la página **Certificados SSL de escucha**, seleccione **Usar un único certificado para esta escucha de web** y, a continuación, haga clic en **Seleccionar certificado**.

16. En el cuadro de diálogo **Seleccionar certificado**, seleccione el certificado que utilizará para esta escucha de web y, a continuación, haga clic en **Seleccionar**.

17. En la página **Certificados SSL de escucha**, haga clic en **Siguiente**.

18. En la página **Configuración de autenticación**, seleccione **Sin autenticación** de la lista desplegable **Seleccionar cómo proporcionan los clientes sus credenciales a Forefront TMG** y, a continuación, haga clic en **Siguiente**.

19. En la página **Configuración de inicio de sesión único**, haga clic en **Siguiente**.

20. En la página **Finalización del Asistente de nueva escucha de web**, revise el resumen de las elecciones de configuración que ha realizado. Cuando esté listo, haga clic en **Finalizar**.

21. En la página **Seleccionar escucha de web**, haga clic en **Siguiente**.

22. En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente puede autenticar directamente** de la lista desplegable **Seleccionar el método utilizado por Forefront TMG para autenticar al servidor web publicado ** y, a continuación, haga clic en **Siguiente**.

23. En la página **Conjuntos de usuarios**, confirme que aparezcan listados los conjuntos de usuarios apropiados. De manera predeterminada, esto es el conjunto de usuarios **Todos los usuarios**. Haga clic en **Agregar** para agregar otros conjuntos de usuarios que haya definido. Cuando haya terminado, haga clic en **Siguiente**.

24. En la página **Finalización del Asistente de nueva regla de publicación web**, haga clic en **Finalizar**.

Tenga en cuenta que hacer clic en **Finalizar** no implica que haya completado el proceso; es decir, esto no aplica automáticamente ni habilita la nueva regla. En cambio, necesitará hacer clic en el botón **Aplicar** que aparecerá en la interfaz de usuario de Forefront TMG. Al hacer clic en **Aplicar** aparecerá el cuadro de diálogo **Descripción de cambio de configuración**. Haga clic en **Aplicar** en ese cuadro de diálogo para habilitar la nueva regla de publicación.

Una vez aplicada la nueva regla, tendrá que realizar algunas modificaciones menores en la regla para asegurarse de que los usuarios puedan usar las nuevas capacidades de presentación de PowerPoint. Para lograr eso, realice el siguiente procedimiento:

1.  En Forefront TMG, haga clic con el botón secundario en el nombre de la nueva regla de publicación y, a continuación, haga clic en **Propiedades**.

2.  En el cuadro de diálogo **Propiedades**, en la pestaña **Para**, seleccione la opción **Reenviar el encabezado de host original en lugar del real**.

3.  En la pestaña **Tráfico**, haga clic en **Filtrar** y, a continuación, haga clic en **Configurar HTTP**.

4.  En el cuadro de diálogo **Configuración de la directiva de HTTP para la regla**, desactive la casilla **Verificar normalización** y, a continuación, haga clic en **Aceptar**.

5.  En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.

6.  En Forefront TMG, haga clic en **Aplicar** para habilitar los cambios. Cuando se abra el cuadro de diálogo **Descripción de cambio de configuración**, haga clic en **Aplicar**.

Una vez finalizada la instalación, puede probar el servidor de Office Web Apps con los procedimientos del tema [Validating The Configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

