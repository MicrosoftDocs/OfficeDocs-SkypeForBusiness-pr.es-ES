---
title: 'Lync Server 2013: Definir la topología perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a04dca4b935caf8f07546babd2c53f65fff4e89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definir la topología perimetral en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Debe usar topología Builder para crear su topología y debe configurar al menos un grupo de servidores front-end interno o un servidor Standard Edition para poder implementar el servidor perimetral. Use el siguiente procedimiento para definir la topología de borde para un único servidor perimetral y, a continuación, use los procedimientos de [publicar su topología en Lync Server 2013](lync-server-2013-publish-your-topology.md) y [exportar su topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar la topología y ponerla a disposición de su servidor perimetral.

<div>


> [!NOTE]  
> La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.



</div>

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins. También puede conceder derechos y permisos de administrador necesarios para agregar roles de servidor a una cuenta de usuario. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.

Si definió la topología de borde cuando definió y publicó su topología interna, y no se necesitan cambios en la topología perimetral que definió anteriormente, no es necesario que la defina y la publique de nuevo. Use el siguiente procedimiento solo si necesita realizar cambios en la topología de borde. Debe hacer que la topología previamente definida y publicada esté disponible para los servidores perimetrales, que puede hacer con el procedimiento de [exportar su topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> No se puede ejecutar el generador de topologías desde un servidor perimetral. Debe ejecutarla desde el servidor front-end o los servidores Standard Edition.



</div>

El proceso para definir la topología del servidor perimetral se realiza en el generador de topología. A continuación, se muestran los tres tipos principales de topologías de servidores perimetrales que se planean y se configuran:

  - Para definir la topología de un único servidor perimetral

  - Para definir la topología de un grupo de servidores perimetrales de carga equilibrada

  - Para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Para definir la topología de un único servidor perimetral

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar un servidor perimetral.

3.  Haga clic con el botón secundario en **agrupaciones perimetrales**y luego haga clic en **nuevo borde**.

4.  En **definir el nuevo grupo de límites**, haga clic en **siguiente**.

5.  En **definir el FQDN del grupo perimetral**, haga lo siguiente:
    
      - En **FQDN del grupo**, escriba el nombre de dominio completo (FQDN) de la interfaz interna para el servidor perimetral.
        
        <div>
        

        > [!IMPORTANT]  
        > El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor. De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. Utilice únicamente caracteres estándar (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado). Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para la compatibilidad con Edge en Lync Server 2013</A>.

        
        </div>
    
      - Haga clic en **grupo de equipos únicos**y, a continuación, en **siguiente**.

6.  En **seleccionar características**, haga lo siguiente:
    
      - Si planea usar un único FQDN e dirección IP para el servicio de acceso SIP, el servicio de conferencias web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un único FQDN e dirección IP** .
    
      - Si planea habilitar la Federación, active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación. Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único. Por ejemplo, si la implementación incluye un grupo perimetral o un solo servidor perimetral implementado en Nueva York y uno implementado en Londres y habilita la compatibilidad con la Federación en el grupo de servidores perimetrales de Nueva York o en el único servidor de borde, la señal de tráfico para usuarios federados pasará por la Nueva York. Grupo Edge o servidor perimetral único. Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.

        
        </div>
    
      - Si tiene previsto admitir el protocolo de presencia y mensajería extensible (XMPP) para su implementación, active la casilla de verificación **Habilitar Federación XMPP (puerto 5269)**

7.  En **seleccionar opciones de IP**, haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.
    
      - **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.
    
      - **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
      - **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
    También puede configurar el servidor perimetral o el grupo Edge para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para ello, active la casilla **la dirección IP externa de este grupo de límites la traduce nat**.

8.  En los **FQDN externos**, haga lo siguiente:
    
      - Si en **seleccionar características** ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba el FQDN externo en el **acceso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si elige esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de Puerto recomendado: 5061 para el servicio perimetral de Access, 444 para el servicio perimetral de conferencias web y 443 para el servicio perimetral de a/V). Seleccionar esta opción puede ayudar a evitar posibles problemas de conectividad y simplificar la configuración, ya que puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

        
        </div>
    
      - Si en **seleccionar características** no ha elegido usar un FQDN y una dirección IP únicos, escriba los FQDN externos para el **acceso SIP**, las **conferencias web** y el **audio video**, manteniendo los puertos predeterminados.

9.  Haga clic en **Siguiente**.

10. En **definir la dirección IP interna**, escriba la dirección IP de su servidor perimetral en la **dirección IPv4 interna** y la **dirección IPv6 interna** , según corresponda a sus necesidades. Haga clic en **Siguiente**.

11. En **definir la dirección IP externa**, haga lo siguiente:
    
      - Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **acceso SIP**y, a continuación, haga clic en **siguiente**.
    
      - Si decide usar direcciones IPv6, escriba la dirección IPv6 externa del servidor perimetral en **acceso SIP**y, a continuación, haga clic en **siguiente**.
    
      - Si no ha elegido usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba las direcciones IPv4 externas del servidor perimetral en **acceso SIP**, **conferencia web**y **Conferencia a/v**y, a continuación, haga clic en **siguiente**.
    
      - Si decide usar direcciones IPv6 y no ha elegido usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba las direcciones IPv6 externas del servidor perimetral en **acceso SIP**, **conferencias web**y **conferencias a/v**y, a continuación, haga clic en **siguiente**.
        
        <div>
        

        > [!NOTE]  
        > Si no ha elegido habilitar ni asignar direcciones IPv6, no podrá ver este cuadro de diálogo.

        
        </div>

12. Si decide usar NAT, aparecerá un cuadro de diálogo. En **dirección IPv4 pública para el servicio a/V Edge**, escriba la dirección IPv4 pública que quiere que traduzca NAT y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Debe ser la dirección IP externa del servicio perimetral A/V.

    
    </div>

13. Si decide usar direcciones NAT e IPv6, aparecerá un cuadro de diálogo. En **dirección IPv6 pública para el servicio a/V Edge**, escriba la dirección IPv6 pública que quiere que traduzca NAT y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Debe ser la dirección IP externa del servicio perimetral A/V.

    
    </div>

14. En **definir el próximo salto**, en **grupo de próximo salto**, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard. O bien, si su implementación incluye un director, seleccione el director. A continuación, haga clic en **siguiente**.

15. En la opción **asociar grupos front end**, especifique uno o varios grupos internos, que pueden incluir grupos de aplicaciones para el usuario y servidores Standard Edition, para que se asocien a este servidor perimetral; para ello, seleccione los nombres de los grupos internos que usarán este servidor perimetral para la comunicación con los usuarios externos admitidos.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asociar un grupo perimetral de carga equilibrada o un único servidor perimetral con cada grupo interno para tráfico de A/V. Si ya tiene un grupo interno asociado con un grupo perimetral o un servidor perimetral, aparece una advertencia que indica que el grupo interno ya está asociado a un grupo perimetral o a un servidor perimetral. Si selecciona un grupo que ya está asociado a otro servidor perimetral, este cambiará la asociación.

    
    </div>

16. Haga clic en **Finalizar**.

17. Publique su topología.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Para definir la topología de un grupo de servidores perimetrales de carga equilibrada de DNS

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar servidores perimetrales.

3.  Haga clic con el botón secundario en **agrupaciones perimetrales**y luego haga clic en **nuevo borde**.

4.  En **definir el nuevo grupo de límites**, haga clic en **siguiente**.

5.  En **definir el FQDN del grupo perimetral**, haga lo siguiente:
    
      - En **FQDN del grupo**, escriba el nombre de dominio completo (FQDN) para la conexión interna del grupo Edge.
        
        <div>
        

        > [!IMPORTANT]  
        > El nombre que especifique para el grupo debe ser el nombre del grupo de bordes interno. Debe definirse como un FQDN. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Utilice únicamente caracteres estándar (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado).

        
        </div>
    
      - Haga clic en **grupo de varios equipos**y, a continuación, en **siguiente**.

6.  En **seleccionar características**, haga lo siguiente:
    
      - Si tiene pensado usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un único FQDN e dirección IP** .
    
      - Si tiene previsto habilitar la Federación, active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** . Haga clic en **siguiente**
        
        <div>
        

        > [!NOTE]  
        > Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación. Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único. Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.

        
        </div>
    
      - Si tiene previsto admitir el protocolo de presencia y mensajería extensible (XMPP) para su implementación, active la casilla de verificación **Habilitar Federación XMPP (puerto 5269)**

7.  Haga clic en **Siguiente**.

8.  En **seleccionar opciones de IP**, haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.
    
      - **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.
    
      - **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
      - **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
    También puede configurar el servidor perimetral o el grupo Edge para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para ello, active la casilla **la dirección IP externa de este grupo de límites la traduce nat**.

9.  En los **FQDN externos**, haga lo siguiente:
    
      - Si en **seleccionar características** ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba el FQDN externo en el **acceso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si elige esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de Puerto recomendado: 5061 para el servicio perimetral de Access, 444 para el servicio perimetral de conferencias web y 443 para el servicio perimetral de a/V). Al seleccionar esta opción, puede ayudar a evitar posibles problemas de conectividad y simplificar la configuración porque puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

        
        </div>
    
      - Si en **seleccionar características** no ha elegido usar un FQDN y una dirección IP únicos, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral para el **acceso por SIP**. En **conferencias web**, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral. En **audio o vídeo**, escriba el nombre de dominio completo que haya elegido para el lado al que se enfrentará el grupo del borde. Use los puertos predeterminados.

10. Haga clic en **Siguiente**.

11. En **definir los equipos de este grupo**, haga clic en **Agregar**.

12. En **nombre completo y dirección IP internos**, haga lo siguiente:
    
      - En **dirección IPv4 interna**, escriba la dirección IPv4 y la **dirección IPv6 interna** , según corresponda a sus requisitos para el primer servidor perimetral que desea crear en este grupo.
    
      - En **nombre de dominio interno**, escriba el FQDN del primer servidor perimetral que desea crear en este grupo.
        
        <div>
        

        > [!NOTE]  
        > El nombre que especifique necesita ser idéntico al nombre del equipo configurado en el servidor. Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. Use solo caracteres estándar (incluidos A-Z, a-z, 0-9 y guiones) al asignar FQDN de sus servidores de Lync, servidores perimetrales, grupos y matrices. No utilice caracteres Unicode ni de subrayado. A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado). Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para la compatibilidad con Edge en Lync Server 2013</A>.

        
        </div>

13. Haga clic en **Siguiente**.

14. En **definir las direcciones IP externas**, haga lo siguiente:
    
      - Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IP externa del servidor perimetral en **acceso de SIP**.
    
      - Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IP que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**. En **conferencias web**, escriba la dirección IP que ha elegido para el lado de la dirección pública de este servidor de la agrupación perimetral. En **conferencia A/V**, escriba la dirección IP que ha elegido para el lado al que va dirigida la pública de este servidor de la agrupación perimetral.

15. Haga clic en **Siguiente**.

16. Si decide habilitar las direcciones IPv6, en **definir las direcciones IP externas**, haga lo siguiente:
    
      - Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **acceso de SIP**.
    
      - Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IPv6 que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**. En **conferencias web**, escriba la dirección IPv6 que haya elegido para el lado al que va dirigida la pública de este servidor de grupo de bordes. En **conferencias A/V**, escriba la dirección IPv6 que ha elegido para el lado al que se enfrenta su público en este servidor de la agrupación perimetral.
    
    <div>
    

    > [!NOTE]  
    > Si no ha elegido habilitar ni asignar direcciones IPv6, no podrá ver este cuadro de diálogo.

    
    </div>

17. Haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Ahora verá el primer servidor perimetral que creó en su grupo en el cuadro de diálogo <STRONG>definir los equipos de este grupo</STRONG> .

    
    </div>

18. En **definir los equipos de este grupo**, haga clic en **Agregar**y, a continuación, repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo de bordes.

19. Después de repetir los pasos 11 a 14, haga clic en **siguiente** en **definir los equipos de este grupo**.
    
    <div>
    

    > [!NOTE]  
    > En este momento, puede ver ambos servidores perimetrales en su grupo.

    
    </div>

20. Si decide usar NAT, aparecerá un cuadro de diálogo. En **dirección IP pública**, escriba las direcciones IPv4 e IPv6 públicas (según corresponda) que NAT va a traducir y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Debe ser la dirección IP externa del borde A/V.

    
    </div>

21. En **definir el próximo salto**, en la lista **siguiente grupo de saltos** , seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo Standard Edition. O bien, si su implementación incluye un director, seleccione el nombre del director. A continuación, haga clic en **siguiente**.

22. En las **agrupaciones front end de Associate**, especifique uno o varios grupos internos, que pueden incluir grupos front-end y servidores Standard Edition, que se asociarán con este servidor perimetral seleccionando los nombres de los pools internos que usarán este servidor perimetral para la comunicación con los usuarios externos admitidos.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asociar un grupo perimetral de carga equilibrada o un único servidor perimetral con cada grupo interno para tráfico de A/V. Si ya tiene un grupo interno asociado con un grupo perimetral o un servidor perimetral, aparece una advertencia que indica que el grupo interno ya está asociado a un grupo perimetral o a un servidor perimetral. Si selecciona un grupo que ya está asociado a otro servidor perimetral, este cambiará la asociación.

    
    </div>

23. Haga clic en **Finalizar**.

24. Publique su topología.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar servidores perimetrales.

3.  Haga clic con el botón secundario en **agrupaciones perimetrales**y seleccione **nuevo grupo perimetral**.

4.  En **definir el nuevo grupo de límites**, haga clic en **siguiente**.

5.  En **definir el FQDN del grupo perimetral**, haga lo siguiente:
    
      - En **FQDN**, escriba el nombre de dominio completo (FQDN) que ha elegido para el lado interno del grupo Edge.
        
        <div>
        

        > [!IMPORTANT]  
        > El nombre que especifique para el grupo debe ser el nombre del grupo de bordes interno. Debe definirse como un FQDN. El Generador de topologías usa nombres de dominio completos, no nombres cortos. Utilice únicamente caracteres estándar (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado).

        
        </div>
    
    <!-- end list -->
    
      - Haga clic en **varios grupos de equipos**y luego en **siguiente**.

6.  En **seleccionar características** , haga lo siguiente:
    
      - Si tiene pensado usar un FQDN y una dirección IP únicos para el servicio de acceso SIP, el servicio de conferencias web de Lync Server y el servicio perimetral A/V, active la casilla **usar un solo FQDN & dirección IP** .
    
      - Si tiene previsto habilitar la Federación, active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación. Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único. Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.

        
        </div>
    
      - Si tiene previsto admitir el protocolo de presencia y mensajería extensible (XMPP) para su implementación, active la casilla de verificación **Habilitar Federación XMPP (puerto 5269)**

7.  Haga clic en **Siguiente**.

8.  En **seleccionar opciones de IP**, haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.
    
      - **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.
    
      - **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
      - **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>No</STRONG> seleccione la casilla de verificación <STRONG>la dirección IP externa del grupo de servidores perimetrales está traducida por NAT</STRONG> . La traducción de direcciones de red (NAT) no es compatible cuando se usa el equilibrio de carga de hardware.

    
    </div>

9.  En los **FQDN externos**, haga lo siguiente:
    
      - Si en **seleccionar características** ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba el FQDN externo en el **acceso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si elige esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de Puerto recomendado: 5061 para el servicio perimetral de Access, 444 para el servicio perimetral de conferencias web y 443 para el servicio perimetral a/V). Al seleccionar esta opción, puede ayudar a evitar posibles problemas de conectividad y simplificar la configuración porque puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

        
        </div>
    
      - Si en **seleccionar características** no ha elegido usar un FQDN y una dirección IP únicos, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral para el **acceso por SIP**. En **conferencias web**, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral. En **audio o vídeo**, escriba el nombre de dominio completo que haya elegido para el lado al que se enfrentará el grupo del borde. Use los puertos predeterminados.
        
        <div>
        

        > [!NOTE]  
        > Estos serán los FQDN de IP virtual (VIP) de orientación pública para el grupo.

        
        </div>

10. Haga clic en **Siguiente**.

11. En **definir los equipos de este grupo**, haga clic en **Agregar**.

12. En **definir las direcciones IP externas**, haga lo siguiente:
    
      - Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral de A/V, escriba la dirección IPv4 externa del servidor perimetral en el **acceso por SIP**. dirección IP externa del servidor perimetral en **acceso de SIP**.
    
      - Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IP que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**. En **conferencias web**, escriba la dirección IP que ha elegido para el lado de la dirección pública de este servidor de la agrupación perimetral. En **conferencia A/V**, escriba la dirección IP que ha elegido para el lado al que va dirigida la pública de este servidor de la agrupación perimetral.

13. Haga clic en **Siguiente**.

14. Si decide habilitar las direcciones IPv6, en **definir las direcciones IP externas**, haga lo siguiente:
    
      - Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **acceso de SIP**.
    
      - Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IPv6 que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**. En **conferencias web**, escriba la dirección IPv6 que haya elegido para el lado al que va dirigida la pública de este servidor de grupo de bordes. En **conferencias A/V**, escriba la dirección IPv6 que ha elegido para el lado al que se enfrenta su público en este servidor de la agrupación perimetral.
    
    <div>
    

    > [!NOTE]  
    > Si no ha elegido habilitar ni asignar direcciones IPv6, no podrá ver este cuadro de diálogo.

    
    </div>

15. Haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Ahora verá el primer servidor perimetral que creó en su grupo en el cuadro de diálogo <STRONG>definir los equipos de este grupo</STRONG> .

    
    </div>

16. En **definir los equipos de este grupo**, haga clic en **Agregar**y, a continuación, repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo perimetral.

17. Después de repetir los pasos 11 a 14, haga clic en **siguiente** en **definir los equipos de este grupo**.
    
    <div>
    

    > [!NOTE]  
    > En este momento, puede ver ambos servidores perimetrales en su grupo.

    
    </div>

18. En **definir el próximo salto**, en la lista **siguiente grupo de saltos** , seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo Standard Edition. O bien, si su implementación incluye un director, seleccione el nombre del director. A continuación, haga clic en **siguiente**.

19. En las **agrupaciones front end de Associate**, especifique uno o varios grupos internos, que pueden incluir grupos front-end y servidores Standard Edition, que se asociarán con este servidor perimetral seleccionando los nombres de los pools internos que usarán este servidor perimetral para la comunicación con los usuarios externos admitidos.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asociar un grupo perimetral de carga equilibrada o un único servidor perimetral con cada grupo interno para tráfico de A/V. Si ya tiene un grupo interno asociado con un grupo perimetral o un servidor perimetral, aparece una advertencia que indica que el grupo interno ya está asociado a un grupo perimetral o a un servidor perimetral. Si selecciona un grupo que ya está asociado a otro servidor perimetral, este cambiará la asociación.

    
    </div>

20. Haga clic en **Finalizar**.

21. Publique su topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

