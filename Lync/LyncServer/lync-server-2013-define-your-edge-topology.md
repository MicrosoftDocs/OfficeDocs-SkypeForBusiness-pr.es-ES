---
title: 'Lync Server 2013: definir la topología perimetral'
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
ms.openlocfilehash: 9bd7c52eef58d4e40c767f48a296a83a8c056525
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definir la topología perimetral en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Debe usar el generador de topologías para crear la topología y debe configurar al menos un grupo de servidores front-end interno o un servidor Standard Edition para poder implementar el servidor perimetral. Use el siguiente procedimiento para definir la topología perimetral para un solo servidor perimetral y, a continuación, use los procedimientos descritos en [Publish Your Topology in Lync server 2013](lync-server-2013-publish-your-topology.md) y [Export your Lync Server 2013 Topology y cópielo en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar la topología y ponerla a disposición de su servidor perimetral.

<div>


> [!NOTE]  
> La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.



</div>

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como usuario miembro de los grupos Administradores del dominio y RTCUniversalServerAdmins. También puede conceder los derechos y permisos de administrador necesarios para agregar roles de servidor a una cuenta de usuario. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.

Si definió la topología perimetral cuando definió y publicó la topología interna y no es necesario modificarla, no tendrá que volver a definirla y publicarla . Use el procedimiento siguiente solo si debe realizar cambios en la topología perimetral. Debe hacer que la topología previamente definida y publicada esté disponible para los servidores perimetrales, lo que lo hace mediante el procedimiento descrito en [exportar su topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> No se puede ejecutar el generador de topologías desde un servidor perimetral. Debe ejecutarlo desde un servidor front-end o servidores Standard Edition.



</div>

El proceso para definir la topología del servidor perimetral se realiza en el generador de topologías. Los tres tipos principales de topologías del servidor perimetral que planea y configura se indican a continuación:

  - Procedimiento para definir la topología de un solo servidor perimetral

  - Procedimiento para definir la topología para un grupo de servidores perimetrales con equilibrio de carga

  - Procedimiento para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Procedimiento para definir la topología de un solo servidor perimetral

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar un servidor perimetral.

3.  Haga clic con el botón secundario en **grupos**de servidores perimetrales y haga clic en **nuevo grupo de servidores perimetrales**.

4.  En **Definir el nuevo grupo de servidores perimetrales**, haga clic en **Siguiente**.

5.  En **Definir el FQDN del grupo perimetral**, haga lo siguiente:
    
      - En **FQDN del grupo de servidores**, escriba el nombre de dominio completo (FQDN) de la interfaz interna del servidor perimetral.
        
        <div>
        

        > [!IMPORTANT]  
        > El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). Topology Builder usa nombres de dominio completos, no nombres cortos. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio. Utilice únicamente caracteres estándar  (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores. No use caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado). Para obtener información detallada sobre cómo agregar un sufijo DNS a un nombre de equipo, vea <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para compatibilidad con servidores perimetrales en Lync Server 2013</A>.

        
        </div>
    
      - Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente**.

6.  En **Seleccionar características**, siga este procedimiento:
    
      - Si planea usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia Web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un solo FQDN y una dirección IP** .
    
      - Si piensa habilitar la federación, active la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

        
        </div>
    
      - Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)**.

7.  En **Seleccionar características de IP**, haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.
    
    También puede configurar el servidor perimetral o el grupo de servidores perimetrales para que usen una dirección de traducción de direcciones de red para las direcciones IP externas. Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.

8.  En **FQDN externos**, siga este procedimiento:
    
      - Si, en **Seleccionar características**, decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

        
        </div>
    
      - Si, en **Seleccionar características**, no eligió la opción de usar un solo FQDN y una dirección IP, escriba los nombres de dominio completos externos de **Acceso SIP**, **Conferencia web** y **Audio/vídeo**, sin cambiar los puertos predeterminados.

9.  Haga clic en **Siguiente**.

10. En **Definir la dirección IP interna**, escriba la dirección IP del servidor perimetral en **Dirección IPv4 interna** y en **Dirección IPv6 interna** según corresponda. Después, haga clic en **Siguiente**.

11. En **Definir la dirección IP externa**, haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **Acceso SIP** y, después, haga clic en **Siguiente**.
    
      - Si decidió usar direcciones IPv6, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP** y haga clic en **Siguiente**.
    
      - Si decidió no usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba las direcciones IPv4 externas del servidor perimetral en **Acceso SIP**, **Conferencia web** y **Conferencia A/V** y, después, haga clic en **Siguiente**.
    
      - Si decidió usar direcciones IPv6 pero no eligió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba las direcciones IPv6 externas del servidor perimetral en **Acceso SIP**, **Conferencia web** y **Conferencia A/V** y, después, haga clic en **Siguiente**.
        
        <div>
        

        > [!NOTE]  
        > Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.

        
        </div>

12. Si decidió usar NAT, aparecerá un cuadro de diálogo. En **Dirección IPv4 pública para el servicio perimetral A/V**, escriba la dirección IPv4 pública que deberá traducir NAT y, después, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Debe ser la dirección IP externa del servicio perimetral A/V.

    
    </div>

13. Si decidió usar NAT y direcciones IPv6, aparecerá un cuadro de diálogo. En **Dirección IPv6 pública para el servicio perimetral A/V**, escriba la dirección IPv6 pública que deberá traducir NAT y, después, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Debe ser la dirección IP externa del servicio perimetral A/V.

    
    </div>

14. En **Definir el próximo salto**, en **Grupo de servidores del próximo salto**, seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o Standard Edition. O, si la implementación incluye un director, selecciónelo. A continuación, haga clic en **Siguiente**.

15. En **Asociar grupos front-end**, especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.

    
    </div>

16. Haga clic en **Finalizar**.

17. Publique la topología.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Procedimiento para definir la topología para un grupo de servidores perimetrales con equilibrio de carga DNS

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar los servidores perimetrales.

3.  Haga clic con el botón secundario en **Grupos de servidores perimetrales ** y, a continuación, en **Nuevo grupo de servidores perimetrales **.

4.  En **Definir el nuevo grupo de servidores perimetrales**, haga clic en **Siguiente**.

5.  En **Definir el FQDN del grupo perimetral**, haga lo siguiente:
    
      - En **FQDN del grupo de servidores**, escriba el nombre de dominio completo (FQDN) de la conexión interna del grupo de servidores perimetrales.
        
        <div>
        

        > [!IMPORTANT]  
        > El nombre que especifique para el grupo de servidores debe ser el nombre del grupo de servidores perimetrales interno. Debe definirse como un FQDN. Topology Builder usa nombres de dominio completos, no nombres cortos. Use únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores. No use caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).

        
        </div>
    
      - Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente**.

6.  En **Seleccionar características**, siga este procedimiento:
    
      - Si planea usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia Web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un solo FQDN y una dirección IP** .
    
      - Si piensa habilitar la federación, active la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Después, haga clic en **Siguiente**.
        
        <div>
        

        > [!NOTE]  
        > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

        
        </div>
    
      - Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)**.

7.  Haga clic en **Siguiente**.

8.  En **Seleccionar características de IP**, haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.
    
    También puede configurar el servidor perimetral o el grupo de servidores perimetrales para que usen una dirección de traducción de direcciones de red para las direcciones IP externas. Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.

9.  En **FQDN externos**, siga este procedimiento:
    
      - Si, en **Seleccionar características**, decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

        
        </div>
    
      - Si, en **Seleccionar características**, no eligió la opción de usar un solo FQDN y una dirección IP, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales en **Acceso SIP**. En **Conferencia web**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. En **Audio/Vídeo**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. Use los puertos predeterminados.

10. Haga clic en **Siguiente**.

11. En **Definir los equipos de este grupo**, haga clic en **Agregar**.

12. En **FQDN y dirección IP internos**, haga lo siguiente:
    
      - En **Dirección IPv4 interna** y en **Dirección IPv6 interna**, escriba las direcciones IPv4 y IPv6 correspondientes del primer servidor perimetral que desea crear en este grupo de servidores.
    
      - En **FQDN interno**, escriba el FQDN del primer servidor perimetral que desea crear en este grupo de servidores.
        
        <div>
        

        > [!NOTE]  
        > El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De forma predeterminada, un equipo no incorporado a un dominio tiene un nombre corto, no un nombre de dominio completo. Topology Builder usa nombres de dominio completos, no nombres cortos. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como un servidor perimetral no unido a un dominio. Utilice únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores. No use caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado). Para obtener información detallada sobre cómo agregar un sufijo DNS a un nombre de equipo, vea <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para compatibilidad con servidores perimetrales en Lync Server 2013</A>.

        
        </div>

13. Haga clic en **Siguiente**.

14. En **Definir las direcciones IP externas**, haga lo siguiente:
    
      - Si decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IP externa del servidor perimetral en **Acceso SIP**.
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.

15. Haga clic en **Siguiente**.

16. Si habilitó las direcciones IPv6, en **Definir las direcciones IP externas** haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP**.
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.
    
    <div>
    

    > [!NOTE]  
    > Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.

    
    </div>

17. Haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Ahora verá el primer servidor perimetral que creó en el grupo de servidores perimetrales, en el cuadro de diálogo <STRONG>Definir los equipos de este grupo</STRONG>.

    
    </div>

18. En **Definir los equipos de este grupo**, haga clic en **Agregar** y, a continuación, repita los pasos del 11 al 14 para agregar el segundo servidor perimetral que desee al grupo de servidores perimetrales.

19. Después de repetir los pasos del 11 al 14, haga clic en **Siguiente** en **Definir los equipos de este grupo**.
    
    <div>
    

    > [!NOTE]  
    > En ese momento, podrá ver ambos servidores perimetrales en el grupo de servidores.

    
    </div>

20. Si decidió usar NAT, aparecerá un cuadro de diálogo. En **Dirección IP pública**, escriba las direcciones IPv4 y IPv6 públicas correspondientes que deberá traducir NAT y, después, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Debe ser la dirección IP externa del servicio perimetral A/V.

    
    </div>

21. En **Definir el próximo salto**, en la lista **Grupo de servidores del próximo salto**, seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard Edition. O, si la implementación incluye un director, seleccione el nombre del director. A continuación, haga clic en **Siguiente**.

22. En **Asociar grupos front-end**, especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.

    
    </div>

23. Haga clic en **Finalizar**.

24. Publique su topología.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Procedimiento para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar los servidores perimetrales.

3.  Haga clic con el botón secundario en grupos de servidores **perimetrales**y seleccione **nuevo grupo de servidores perimetrales**.

4.  En **Definir el nuevo grupo de servidores perimetrales**, haga clic en **Siguiente**.

5.  En **Definir el FQDN del grupo de servidores perimetrales**, haga lo siguiente:
    
      - En **FQDN**, escriba el nombre de dominio completo (FQDN) que haya elegido para el lado interno del grupo de servidores perimetrales.
        
        <div>
        

        > [!IMPORTANT]  
        > El nombre que especifique para el grupo de servidores debe ser el nombre del grupo de servidores perimetrales interno. Debe definirse como un FQDN. Topology Builder usa nombres de dominio completos, no nombres cortos. Use únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).

        
        </div>
    
    <!-- end list -->
    
      - Haga clic en **grupo de varios equipos**y, a continuación, en **siguiente**.

6.  En **Seleccionar características**, haga lo siguiente:
    
      - Si planea usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia Web de Lync Server y el servicio perimetral A/V, active la casilla **usar un solo FQDN & dirección IP** .
    
      - Si piensa habilitar la federación, active la casilla **Habilitar federación (puerto 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

        
        </div>
    
      - Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)**.

7.  Haga clic en **Siguiente**.

8.  En **Seleccionar características de IP**, haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.
    
      - **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>No</STRONG> active la casilla <STRONG>La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT</STRONG>. La traducción de direcciones de red (NAT) no es compatible con el uso del equilibrio de carga de hardware.

    
    </div>

9.  En **FQDN externos**, haga lo siguiente:
    
      - Si, en **Seleccionar características** decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

        
        </div>
    
      - Si, en **Seleccionar características**, no eligió la opción de usar un solo FQDN y una dirección IP, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales en **Acceso SIP**. En **Conferencia web**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. En **Audio/Vídeo**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. Use los puertos predeterminados.
        
        <div>
        

        > [!NOTE]  
        > Serán los nombres de dominio completos de IP virtual (VIP) de cara al público del grupo de servidores.

        
        </div>

10. Haga clic en **Siguiente**.

11. En **Definir los equipos de este grupo**, haga clic en **Agregar**.

12. En **Definir las direcciones IP externas**, haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **acceso SIP**. dirección IP externa del servidor perimetral en **acceso SIP**.
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.

13. Haga clic en **Siguiente**.

14. Si habilitó las direcciones IPv6, en **Definir las direcciones IP externas** haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP**.
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.
    
    <div>
    

    > [!NOTE]  
    > Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.

    
    </div>

15. Haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > Verá el primer servidor perimetral que ha creado en el grupo de servidores en el cuadro de diálogo <STRONG>Definir los equipos de este grupo de servidores</STRONG>.

    
    </div>

16. En **Definir los equipos de este grupo de servidores**, haga clic en **Agregar** y repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo de servidores perimetrales.

17. Después de repetir los pasos 11 a 14, haga clic en **Siguiente** en **Definir los equipos de este grupo de servidores**.
    
    <div>
    

    > [!NOTE]  
    > En ese momento, podrá ver ambos servidores perimetrales en el grupo de servidores.

    
    </div>

18. En **Definir el próximo salto**, en la lista **Grupo de servidores del próximo salto**, seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard Edition. O, si la implementación incluye un director, escriba el nombre del director. A continuación, haga clic en **Siguiente**.

19. En **Asociar grupos front-end**, especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.

    
    </div>

20. Haga clic en **Finalizar**.

21. Publique la topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

