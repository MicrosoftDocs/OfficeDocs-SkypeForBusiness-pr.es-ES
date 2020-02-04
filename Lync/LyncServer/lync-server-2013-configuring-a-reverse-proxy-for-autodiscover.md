---
title: 'Lync Server 2013: configuración de un proxy inverso para detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a02bf765941c7240f08fecc91d5912f31a0f2f87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>Configuración de un proxy inverso para detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

La detección automática y la compatibilidad de clientes que usan detección automática requieren la modificación de una regla de publicación de web existente o la creación de una nueva regla de publicación web para el proxy inverso. La modificación o la creación de una nueva regla de publicación no depende de la decisión de actualizar o no actualizar las listas de nombres alternativos de asunto en los certificados de proxy inverso.

Si decide usar HTTPS para las solicitudes de servicio de detección automática de Lync Server 2013 y actualizar las listas de nombres alternativos de asunto en los certificados de proxy inverso, debe asignar el certificado público actualizado a la escucha de capa de sockets seguros (SSL) en su proxy inverso. La actualización requerida para el certificado externo (público) incluirá la entrada de nombre alternativo de asunto (SAN) para lyncdiscover. \<nombre\>de dominio. A continuación, debe modificar el agente de escucha existente para los servicios web externos o crear una nueva regla de publicación de web para la dirección URL del servicio de detección automática externa, por ejemplo **lyncdiscover.contoso.com**. Si todavía no tiene una regla de publicación web para la dirección URL externa de servicios Web de Lync Server 2013 para el grupo de servidores front-end y el grupo de directores (si ha implementado directores), también tendrá que publicar una regla para ello.

<div>


> [!NOTE]  
> La regla de publicación y la escucha de proxy inversos pueden atender tanto los servicios web externos como el servicio Detección automática, siempre que el certificado asignado a la escucha contenga el nombre de asunto y los nombres alternativos de asunto necesarios para ambos. Para obtener más información sobre la configuración predeterminada de la escucha de web y la regla de publicación, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync Server 2013</A> para obtener más información.



</div>

Si decide usar HTTP para las solicitudes de servicio de detección automática iniciales, de modo que no necesite actualizar nombres alternativos de asunto para el proxy inverso, debe crear o modificar una regla de publicación web para el puerto 80.

Los procedimientos de esta sección describen cómo crear o modificar las reglas de publicación web en Microsoft Forefront Threat Management Gateway 2010 para el descubrimiento automático.

<div>


> [!NOTE]  
> En estos procedimientos se supone que ha instalado la edición estándar de Forefront Threat Management Gateway (TMG) 2010. Si está usando otro proxy inverso, los procedimientos son similares, pero deberán asignarse a la documentación del producto de terceros.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Para crear una regla de publicación web para la dirección URL externa de detección automática

1.  Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de Firewall**, seleccione **nuevo**y, después, haga clic en regla de **publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación de web** , escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, LyncDiscoveryURL).

4.  En la página **Seleccionar acción de regla** , seleccione **permitir**.

5.  En la página **tipo de publicación** , seleccione **publicar un único sitio web o un equilibrador de carga**.

6.  En la página **seguridad de conexión de servidor** , seleccione **usar SSL para conectarse al servidor web o conjunto**de servidores publicado.

7.  En la página **Internal Publishing details** , en **nombre de sitio interno**, escriba el nombre de dominio completo (FQDN) de su grupo de directores (por ejemplo, lyncdir01. contoso. local). Si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, escriba el FQDN del grupo de servidores front-end (por ejemplo, lyncpool01. contoso. local).

8.  En la **página datos internos de publicación** , en **ruta de acceso (opcional)**, escriba ** / ** la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **reenviar el encabezado de host original**.

9.  En la página **detalles de nombre público** , haga lo siguiente:
    
      - En **aceptar solicitudes por**, seleccione **este nombre de dominio**.
    
      - En **nombre público**, escriba **lyncdiscover.** \<sipdomain\> (dirección URL externa del servicio de detección automática). Si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, escriba el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).
    
      - En **ruta**de acceso ** / **, escriba.

10. En la página **seleccionar escucha de web** , en **escucha de web**, seleccione la escucha SSL existente con el certificado público actualizado.

11. En la página **delegación de autenticación** , seleccione **sin delegación, pero el cliente puede autenticar directamente**.

12. En la página **conjunto de usuarios** , seleccione **todos los usuarios**.

13. En la página **finalización del Asistente para nueva regla de publicación de web** , compruebe que la configuración de la regla de publicación de web es correcta y, a continuación, haga clic en **Finalizar**.

14. En la lista de reglas de publicación Web de Forefront TMG, haga doble clic en la nueva regla que acaba de agregar para abrir **propiedades**.

15. En la pestaña **para** , haga lo siguiente:
    
      - Seleccione **reenviar el encabezado de host original en lugar del real**.
    
      - **Las solicitudes Select parecen proceder del equipo FOREFRONT TMG**.

16. En la pestaña **puente** , configure lo siguiente:
    
      - Seleccione **servidor Web**.
    
      - Seleccione **redirigir las solicitudes al puerto http**y escriba **8080** para el número de puerto.
    
      - Seleccione **redirigir peticiones al puerto SSL**y escriba **4443** para el número de puerto.

17. Haga clic en **Aceptar**.

18. Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

19. Haga clic en **probar regla** para comprobar que la nueva regla está configurada correctamente.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Para modificar una regla de publicación web existente para agregar el SAN y la dirección URL de detección automática externa

1.  Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.
    
    <div>
    

    > [!IMPORTANT]  
    > Repetirá la modificación para cada regla de publicación y agente de escucha que tenga. Por lo general, será una regla y una escucha para los grupos de aplicaciones para el usuario y otra para los grupos opcionales o grupos de directores, si se han implementado.

    
    </div>

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón derecho en **Directiva de Firewall**, haga clic en la regla correspondiente. En la pestaña **tareas** , haga clic en **Editar regla seleccionada**.

3.  En la pestaña **nombre público** , en **esta regla se aplica a**, seleccione **solicitudes para los siguientes sitios web**.

4.  Haga clic en **Agregar**, escriba el nombre del nuevo sitio de Autodiscover (por ejemplo, "lyncdiscover.contoso.com") y, a continuación, haga clic en **Aceptar**.

5.  En la pestaña **agente de escucha** , haga clic en **seleccionar certificado** y asigne el nuevo certificado con las entradas de San de detección automática agregadas. Cierre las propiedades de escucha y publicación de Web.

6.  Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

7.  Haga clic en **probar regla** para comprobar que la nueva regla está configurada correctamente.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Para crear una regla de publicación web para el puerto 80

1.  Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de Firewall**, seleccione **nuevo**y, después, haga clic en regla de **publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación de web** , escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, Lync Autodiscover (http)).

4.  En la página **Seleccionar acción de regla** , seleccione **permitir**.

5.  En la página **tipo de publicación** , seleccione **publicar un único sitio web o un equilibrador de carga**.

6.  En la página **seguridad de conexión de servidor** , seleccione **usar conexiones no seguras para conectarse al servidor web o conjunto**de servidores publicado.

7.  En la página **Internal Publishing details** , en **nombre de sitio interno**, escriba el FQDN de los servicios Web internos de su grupo de front-end (por ejemplo, lyncpool01. contoso. local).

8.  En la **página datos internos de publicación** , en **ruta de acceso (opcional)**, escriba ** / ** la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **reenviar el encabezado de host original en lugar del especificado en el campo Nombre del sitio interno**.

9.  En la página **detalles de nombre público** , haga lo siguiente:
    
      - En **aceptar solicitudes por**, seleccione **este nombre de dominio**.
    
      - En **nombre público**, escriba **lyncdiscover.** \<sipdomain\> (dirección URL externa del servicio de detección automática).
    
      - En **ruta**de acceso ** / **, escriba.

10. En la página **seleccionar escucha de web** , en **escucha de web**, seleccione una escucha de web o use el Asistente para definición de escuchas de Web nuevo para crear una nueva.

11. En la página **delegación de autenticación** , seleccione **sin delegación y el cliente no puede autenticar directamente**.

12. En la página **conjunto de usuarios** , seleccione **todos los usuarios**.

13. En la página **finalización del Asistente para nueva regla de publicación de web** , compruebe que la configuración de la regla de publicación de web es correcta y, a continuación, haga clic en **Finalizar**.

14. En la lista de reglas de publicación Web de Forefront TMG, haga doble clic en la nueva regla que acaba de agregar para abrir **propiedades**.

15. En la pestaña **puente** , configure lo siguiente:
    
      - Seleccione **servidor Web**.
    
      - Seleccione **redirigir las solicitudes al puerto http**y escriba **8080** para el número de puerto.
    
      - Compruebe que el **puerto SSL de redirección** no está seleccionado.

16. Haga clic en **Aceptar**.

17. Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

18. Haga clic en **probar regla** para comprobar que la nueva regla está configurada correctamente.

19. Compruebe que la dirección URL del servicio de detección automática externa no esté definida en ninguna otra regla de publicación de Web.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de los servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

