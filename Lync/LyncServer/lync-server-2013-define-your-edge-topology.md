---
title: 'Lync Server 2013: Definir la topología perimetral'
TOCTitle: Definir la topología perimetral
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48275744
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir la topología perimetral en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-28_

Debe usar Generador de topologías para crear la topología e instalar, al menos, un servidor Standard Edition o un grupo de servidores front-end interno antes de poder implementar el servidor perimetral. Siga el procedimiento que se indica a continuación para definir la topología perimetral de un solo servidor perimetral y, a continuación, siga los procedimientos de [Publicar una topología en Lync Server 2013](lync-server-2013-publish-your-topology.md) y [Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar la topología y ponerla a disposición del servidor perimetral.


> [!NOTE]
> La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.



Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como usuario miembro de los grupos Administradores del dominio y RTCUniversalServerAdmins. También puede conceder los derechos y permisos de administrador necesarios para agregar roles de servidor a una cuenta de usuario. Para obtener información detallada, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación referente a la implementación de servidores Standard Edition o Enterprise Edition. Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.

Si definió la topología perimetral cuando definió y publicó la topología interna y no es necesario modificarla, no tendrá que volver a definirla y publicarla. Use el procedimiento siguiente solo si debe realizar cambios en la topología perimetral. Deberá poner la topología definida y publicada previamente disponible para los servidores perimetral mediante el procedimiento descrito en [Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

> [!IMPORTANT]  
> No se puede ejecutar Generador de topologías desde un servidor perimetral. Debe ejecutarlo desde un servidor front-end o servidores Standard Edition.



El proceso para definir la topología del servidor perimetral se realiza en Generador de topologías. Los tres tipos principales de topologías del servidor perimetral que planea y configura se indican a continuación:

  - Procedimiento para definir la topología de un solo servidor perimetral

  - Procedimiento para definir la topología para un grupo de servidores perimetrales con equilibrio de carga

  - Procedimiento para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

## Procedimiento para definir la topología de un solo servidor perimetral

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar un servidor perimetral.

3.  Haga clic con el botón derecho en **Grupos de servidores perimetrales** y luego haga clic en **Nuevo grupo de servidores perimetrales**.

4.  En **Definir el nuevo grupo de servidores perimetrales** , haga clic en **Siguiente** .

5.  En **Definir el FQDN del grupo de servidores perimetrales** , haga lo siguiente:
    
      - En **FQDN del grupo de servidores** , escriba el nombre de dominio completo (FQDN) de la interfaz interna del servidor perimetral.
        
        > [!IMPORTANT]  
        > El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). El Generador de topologías utiliza nombres de dominio completos, en vez de nombres cortos. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como un servidor perimetral no unido a un dominio. Utilice únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado). Para obtener información detallada sobre cómo agregar un sufijo DNS al nombre de equipo, vea <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar DNS para admitir servidores perimetrales en Lync Server 2013</a>.
        
    
      - Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente** .

6.  En **Seleccionar características** , siga este procedimiento:
    
      - Si piensa usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **Usar un solo FQDN y una dirección IP** .
    
      - Si piensa habilitar la federación, active la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** .
        

        > [!NOTE]
        > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

    
      - Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)** .

7.  En **Seleccionar características de IP** , haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna** : active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv6 en la interfaz interna** : active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv4 en la interfaz externa** : active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv6 en la interfaz externa** : active la casilla si desea aplicar una dirección IPv6 a la interfaz externa del Servidor perimetral o el Grupo de servidores perimetrales
    
    También puede configurar el Servidor perimetral o el Grupo de servidores perimetrales para usar la traducción de direcciones de red en las direcciones IP externas. Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT** .

8.  En **FQDN externos** , haga lo siguiente:
    
      - Si, en **Seleccionar características** decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP** .
        

        > [!NOTE]
        > Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

    
      - Si, en **Seleccionar características** , no eligió la opción de usar un solo FQDN y una dirección IP, escriba los nombres de dominio completos externos de **Acceso SIP** , **Conferencia web** y **Audio/vídeo** , sin cambiar los puertos predeterminados.

9.  Después, haga clic en **Siguiente** .

10. En **Definir la dirección IP interna** , escriba la dirección IP del servidor perimetral en **Dirección IPv4 interna** y en **Dirección IPv6 interna** según corresponda. Después, haga clic en **Siguiente** .

11. En **Definir la dirección IP externa** , haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **Acceso SIP** y, después, haga clic en **Siguiente** .
    
      - Si decidió usar direcciones IPv6, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP** y haga clic en **Siguiente** .
    
      - Si decidió no usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba las direcciones IPv4 externas del servidor perimetral en **Acceso SIP** , **Conferencia web** y **Conferencia A/V** y, después, haga clic en **Siguiente** .
    
      - Si decidió usar direcciones IPv6 pero no eligió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba las direcciones IPv6 externas del servidor perimetral en **Acceso SIP** , **Conferencia web** y **Conferencia A/V** y, después, haga clic en **Siguiente** .
        

        > [!NOTE]
        > Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.



12. Si decidió usar NAT, aparecerá un cuadro de diálogo. En **Dirección IPv4 pública para el servicio perimetral A/V** , escriba la dirección IPv4 pública que deberá traducir NAT y, después, haga clic en **Siguiente** .
    

    > [!NOTE]
    > Debe ser la dirección IP externa del servicio perimetral A/V.



13. Si decidió usar NAT y direcciones IPv6, aparecerá un cuadro de diálogo. En **Dirección IPv6 pública para el servicio perimetral A/V** , escriba la dirección IPv6 pública que deberá traducir NAT y, después, haga clic en **Siguiente** .
    

    > [!NOTE]
    > Debe ser la dirección IP externa del servicio perimetral A/V.



14. En **Definir el próximo salto** , en **Grupo de servidores del próximo salto** , seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o Standard Edition. O, si la implementación incluye un director, selecciónelo. A continuación, haga clic en **Siguiente** .

15. En **Asociar grupos front-end** , especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.
    

    > [!NOTE]
    > Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.



16. Haga clic en **Finalizar** .

17. Publique la topología.

## Procedimiento para definir la topología para un grupo de servidores perimetrales con equilibrio de carga DNS

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar servidores perimetrales.

3.  Haga clic con el botón derecho en **Grupos de servidores perimetrales** y luego en **Nuevo grupo de servidores perimetrales**.

4.  En **Definir el nuevo grupo de servidores perimetrales** , haga clic en **Siguiente** .

5.  En **Definir el FQDN del grupo de servidores perimetrales** , haga lo siguiente:
    
      - En **FQDN del grupo de servidores** , escriba el nombre de dominio completo (FQDN) de la conexión interna del grupo de servidores perimetrales.
        
        > [!IMPORTANT]  
        > El nombre que especifique para el grupo de servidores debe ser idéntico al del grupo de servidores perimetrales interno. Debe especificarse como un FQDN, ya que el Generador de topologías utiliza nombres FQDN, no nombres cortos. Así pues, use únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne FQDN de los servidores Lync Server, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Normalmente los DNS externos y las entidades de certificación (CA) públicas no admiten caracteres que no sean estándar en el nombre FQDN (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).
        
    
      - Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente** .

6.  En **Seleccionar características** , siga este procedimiento:
    
      - Si piensa usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **Usar un solo FQDN y una dirección IP** .
    
      - Si piensa habilitar la federación, active la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** . Después, haga clic en **Siguiente** .
        

        > [!NOTE]
        > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

    
      - Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)** .

7.  Después, haga clic en **Siguiente** .

8.  En **Seleccionar características de IP** , haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna** : active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv6 en la interfaz interna** : active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv4 en la interfaz externa** : active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv6 en la interfaz externa** : active la casilla si desea aplicar una dirección IPv6 a la interfaz externa del Servidor perimetral o el Grupo de servidores perimetrales
    
    También puede configurar el Servidor perimetral o el Grupo de servidores perimetrales para usar la traducción de direcciones de red en las direcciones IP externas. Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT** .

9.  En **FQDN externos** , haga lo siguiente:
    
      - Si, en **Seleccionar características** , decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP** .
        

        > [!NOTE]
        > Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

    
      - Si, en **Seleccionar características** , no eligió la opción de usar un solo FQDN y una dirección IP, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales en **Acceso SIP** . En **Conferencia web** , escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. En **Audio/Vídeo** , escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. Use los puertos predeterminados.

10. Después, haga clic en **Siguiente** .

11. En **Definir los equipos de este grupo** , haga clic en **Agregar** .

12. En **FQDN y dirección IP internos** , haga lo siguiente:
    
      - En **Dirección IPv4 interna** y en **Dirección IPv6 interna** , escriba las direcciones IPv4 y IPv6 correspondientes del primer servidor perimetral que desea crear en este grupo de servidores.
    
      - En **FQDN interno** , escriba el FQDN del primer servidor perimetral que desea crear en este grupo de servidores.
        

        > [!NOTE]
        > El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). El Generador de topologías utiliza nombres de dominio completos, en vez de nombres cortos. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como un servidor perimetral no unido a un dominio. Utilice únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado). Para obtener información detallada sobre cómo agregar un sufijo DNS al nombre de equipo, vea <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar DNS para admitir servidores perimetrales en Lync Server 2013</A>.



13. Después, haga clic en **Siguiente** .

14. En **Definir las direcciones IP externas** , haga lo siguiente:
    
      - Si decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IP externa del servidor perimetral en **Acceso SIP** .
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP** . En **Conferencia web** , escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V** , escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.

15. Después, haga clic en **Siguiente** .

16. Si habilitó las direcciones IPv6, en **Definir las direcciones IP externas** haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP** .
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP** . En **Conferencia web** , escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V** , escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.
    

    > [!NOTE]
    > Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.



17. Haga clic en **Finalizar** .
    

    > [!NOTE]
    > Verá el primer servidor perimetral que ha creado en el grupo de servidores en el cuadro de diálogo <STRONG>Definir los equipos de este grupo de servidores</STRONG> .



18. En **Definir los equipos de este grupo** , haga clic en **Agregar** y, a continuación, repita los pasos del 11 al 14 para agregar el segundo servidor perimetral que desee al grupo de servidores perimetrales.

19. Después de repetir los pasos 11 a 14, haga clic en **Siguiente** en **Definir los equipos de este grupo de servidores** .
    

    > [!NOTE]
    > En ese momento, podrá ver ambos servidores perimetrales en el grupo de servidores.



20. Si decidió usar NAT, aparecerá un cuadro de diálogo. En **Dirección IP pública** , escriba las direcciones IPv4 y IPv6 públicas correspondientes que deberá traducir NAT y, después, haga clic en **Siguiente** .
    

    > [!NOTE]
    > Debe ser la dirección IP externa del servicio perimetral A/V.



21. En **Definir el próximo salto** , en la lista **Grupo de servidores del próximo salto** , seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard Edition. O, si la implementación incluye un director, escriba el nombre del director. A continuación, haga clic en **Siguiente** .

22. En **Asociar grupos front-end** , especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.
    

    > [!NOTE]
    > Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.



23. Haga clic en **Finalizar** .

24. Publique la topología.

## Procedimiento para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda el sitio en el que desea implementar servidores perimetrales.

3.  Haga clic con el botón secundario en **Grupos de servidores perimetrales** y seleccione **Nuevo grupo de servidores perimetrales** .

4.  En **Definir el nuevo grupo de servidores perimetrales** , haga clic en **Siguiente** .

5.  En **Definir el FQDN del grupo de servidores perimetrales** , haga lo siguiente:
    
      - En **FQDN** , escriba el nombre de dominio completo (FQDN) que haya elegido para el lado interno del grupo de servidores perimetrales.
        
        > [!IMPORTANT]  
        > El nombre que especifique para el grupo de servidores debe ser idéntico al del grupo de servidores perimetrales interno. Debe especificarse como un FQDN, ya que el Generador de topologías utiliza nombres FQDN, no nombres cortos. Así pues, use únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne FQDN de los servidores Lync Server, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Normalmente los DNS externos y las entidades de certificación (CA) públicas no admiten caracteres que no sean estándar en el nombre FQDN (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).
        
    
    <!-- end list -->
    
      - Haga clic en **Grupo de servidores de varios equipos** y, a continuación, en **Siguiente** .

6.  En **Seleccionar características** , haga lo siguiente:
    
      - Si va a usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Lync Server y el servicio perimetral A/V, active la casilla **Usar un solo nombre de dominio completo y dirección IP** .
    
      - Si piensa habilitar la federación, active la casilla **Habilitar federación (puerto 5061)** .
        

        > [!NOTE]
        > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

    
      - Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)** .

7.  Después, haga clic en **Siguiente** .

8.  En **Seleccionar características de IP** , haga lo siguiente:
    
      - **Habilitar IPv4 en la interfaz interna** : active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv6 en la interfaz interna** : active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv4 en la interfaz externa** : active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del Servidor perimetral o el Grupo de servidores perimetrales
    
      - **Habilitar IPv6 en la interfaz externa** : active la casilla si desea aplicar una dirección IPv6 a la interfaz externa del Servidor perimetral o el Grupo de servidores perimetrales
    
    > [!IMPORTANT]  
    > <strong>No</strong> active la casilla <strong>La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT</strong> . La traducción de direcciones de red (NAT) no es compatible con el uso del equilibrio de carga de hardware.
    


9.  En **FQDN externos** , haga lo siguiente:
    
      - Si, en **Seleccionar características** decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP** .
        

        > [!NOTE]
        > Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.

    
      - Si, en **Seleccionar características** , no eligió la opción de usar un solo FQDN y una dirección IP, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales en **Acceso SIP** . En **Conferencia web** , escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. En **Audio/Vídeo** , escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. Use los puertos predeterminados.
        

        > [!NOTE]
        > Serán los nombres de dominio completos de IP virtual (VIP) de cara al público del grupo de servidores.



10. Después, haga clic en **Siguiente** .

11. En **Definir los equipos de este grupo** , haga clic en **Agregar** .

12. En **Definir las direcciones IP externas** , haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IP externa del servidor perimetral en **Acceso SIP**. Dirección IP externa del servidor perimetral en **Acceso SIP**.
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP** . En **Conferencia web** , escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V** , escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.

13. Después, haga clic en **Siguiente** .

14. Si habilitó las direcciones IPv6, en **Definir las direcciones IP externas** haga lo siguiente:
    
      - Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP** .
    
      - Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP** . En **Conferencia web** , escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V** , escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.
    

    > [!NOTE]
    > Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.



15. Haga clic en **Finalizar** .
    

    > [!NOTE]
    > Verá el primer servidor perimetral que ha creado en el grupo de servidores en el cuadro de diálogo <STRONG>Definir los equipos de este grupo de servidores</STRONG> .



16. En **Definir los equipos de este grupo de servidores** , haga clic en **Agregar** y repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo de servidores perimetrales.

17. Después de repetir los pasos 11 a 14, haga clic en **Siguiente** en **Definir los equipos de este grupo de servidores** .
    

    > [!NOTE]
    > En ese momento, podrá ver ambos servidores perimetrales en el grupo de servidores.



18. En **Definir el próximo salto** , en la lista **Grupo de servidores del próximo salto** , seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard Edition. O, si la implementación incluye un director, escriba el nombre del director. A continuación, haga clic en **Siguiente** .

19. En **Asociar grupos front-end** , especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.
    

    > [!NOTE]
    > Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.



20. Haga clic en **Finalizar** .

21. Publique la topología.

