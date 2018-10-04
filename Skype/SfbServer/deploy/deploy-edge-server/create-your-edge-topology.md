---
title: Creación de la topología perimetral para Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumen: Obtenga información sobre cómo crear, publicar y exportar la topología de servidor perimetral de Skype para Business Server.'
ms.openlocfilehash: b01f0c107207d79f62a092acc2e287e632969234
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372776"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Creación de la topología perimetral para Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo crear, publicar y exportar la topología de servidor perimetral de Skype para Business Server.
  
Generador de topología es la herramienta que se debe usar para crear la topología de servidor perimetral, al igual que se usa para cualquier componente de la topología de Skype para Business Server. Antes de seguir los pasos siguientes, necesita ha configurado al menos un grupo de servidores Front-End o un servidor Standard Edition.
  
Se tratarán los siguientes temas en este artículo:
  
- Crear la topología de servidor perimetral
    
- Publicar la topología del servidor perimetral
    
- Exportar la topología del servidor perimetral
    
  > [!NOTE]
  > Para seguir los pasos que se indican a continuación, tendrá que iniciar sesión en los servidores del dominio mencionados a continuación como un usuario que es miembro de los siguientes grupos de dominio: 
  
- RTCUniversalServerAdmins
    
- Administradores de dominio
    
## <a name="build-your-edge-server-topology"></a>Crear la topología de servidor perimetral

El primer paso de implementación está creando su Skype para la topología de servidor perimetral de Business Server, que se compone de uno de tres opciones:
  
- Un solo servidor perimetral
    
- Un grupo de servidores DNS con equilibrio de carga perimetrales (uno o varios servidores)
    
- Grupo de servidores perimetrales (uno o varios servidores) con equilibrio de carga del hardware
    
Si no está seguro de qué necesita, siga estos pasos antes de empezar, es un buen momento para ver la documentación de la planeación. De lo contrario, comencemos.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definición de la topología de un solo servidor perimetral

1. Inicie sesión en su Skype para Business Server Standard Edition o un Skype para grupo de negocio de servidor Front-End.
    
2. Una vez allí, abra **Skype para Business Server Topology Builder**.
    
3. En el árbol de consola, expanda el sitio que va a implementar el servidor perimetral a.
    
4. Haga clic en **grupos de servidores perimetrales**y, a continuación, haga clic en **grupo de servidores perimetrales de nuevo**.
    
5. Aquí clic en **siguiente** en la pantalla de **grupo de servidores perimetrales nueva definir** .
    
6. En la pantalla **definir el FQDN del grupo de servidores perimetrales** , escriba el nombre de dominio completo (FQDN) interno que el servidor perimetral se va a usar y seleccione **el grupo de servidores de un solo equipo**, haga clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
   - Es posible que desea utilizar la misma dirección IP y FQDN para el servicio de acceso SIP, su Skype para el servicio de conferencia Web de Business Server y su / servicio perimetral A/v. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
   - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
   Estos son bastante fácil de entender, si está utilizando las direcciones IPv4 o IPv6, y va a aplicar esas direcciones en el servidor perimetral interna o externamente (que necesitará para tener en cuenta para el paso 10). También tiene la opción de configuración de su servidor perimetral o grupo de servidores perimetrales para usar una dirección de traducción (NAT) de dirección de red para la dirección IP externa. Para ello, puede seleccionar la casilla **La dirección IP externa de este grupo de servidores perimetrales se traduce con NAT**. Haga clic en **Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activa la casilla de verificación **usar una dirección IP y FQDN único** , debe escribir el FQDN externo único en el cuadro **Acceso SIP** . A continuación, deberá escribir los números de puerto diferente para cada servicio perimetral para permitir que todos ellos para conectarse de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla de verificación **usar una única dirección IP y FQDN** , ahora deberá escribir el FQDN externos tres para el servicio perimetral de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio perimetral. Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora está en la pantalla de **definir la dirección IP interna** . Aquí se tendrá que escribir la dirección IP del servidor perimetral en los cuadros de texto **dirección IPv4 interna** y la **dirección IPv6 interno** , según las opciones seleccionadas en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
11. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (lo que está usando) en el cuadro de texto de **Acceso SIP** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio perimetral y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
12. Si opta por utilizar NAT en el paso 8, ahora aparecerá una pantalla con un cuadro de texto **dirección IP pública** . Debe escribir la dirección IPv4 o IPv6 pública ha establecido para el / servicio perimetral A/v, que se debe traducir por NAT. Luego, haga clic en **Siguiente**.
    
13. La siguiente pantalla es **Definir el próximo salto**. En el cuadro de **grupo del próximo salto** , seleccione el nombre de su grupo de servidores interno, es posible que un grupo de servidores Front-End o un grupo de servidores independientes. Si tiene un Director en su entorno, debe elegir el Director. Then click **Next**.
    
14. En la pantalla **grupos asociar Front-End** , debe especificar uno o varios grupos de servidores internos, incluidos los grupos de servidores Front-End y servidores Standard Edition, para asociar con este servidor perimetral. Sólo tiene que elegir los nombres de los grupos de servidores internos que desea usar este servidor perimetral para comunicarse con usuarios externos admitidos. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo a tener en cuenta aquí es, si los servidores de independientes o grupos de servidores internos utilizan ya un Skype diferente para el servidor perimetral de Business Server, no pueden tener varias asociaciones. Si elige un grupo de servidores interno o un servidor independiente que se encuentra en esa situación, verá aparecer una advertencia de error que informa sobre el otro servidor perimetral, y puede decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
15. Haga clic en **Finalizar** en la pantalla siguiente.
    
16. Ahora podrá publicar esta tecnología actualizada y siga las instrucciones de [Implementación de servidores perimetrales en Skype para Business Server](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definición de la topología para un DNS con equilibrio de carga grupo de servidores perimetrales

1. Inicie sesión en su Skype para Business Server Standard Edition o un Skype para Business Server Front-End Server.
    
2. Una vez allí, abra **Skype para Business Server Topology Builder**.
    
3. En el árbol de consola, expanda el sitio que va a implementar el servidor perimetral a.
    
4. Haga clic en **grupos de servidores perimetrales**y, a continuación, haga clic en **grupo de servidores perimetrales de nuevo**.
    
5. Aquí clic en **siguiente** en la pantalla de **grupo de servidores perimetrales nueva definir** .
    
6. En la pantalla **definir el FQDN del grupo de servidores perimetrales** , escriba el nombre de dominio completo (FQDN) interno que el grupo de servidores perimetrales se va a usar y, seleccione **el grupo de servidores de varios equipos**, al hacer clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
    - Desea usar la misma dirección IP y FQDN para su servicio de acceso SIP, su Skype Business Server Web servicio de conferencia y su / servicio perimetral A/v. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
    - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
    - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estos son bastante fácil de entender, si está utilizando las direcciones IPv4 o IPv6, y va a aplicar esas direcciones en el servidor perimetral interna o externamente (que necesitará para tener en cuenta para el paso 11). También tiene la opción de configuración de su servidor perimetral o grupo de servidores perimetrales para usar una dirección de traducción (NAT) de dirección de red para la dirección IP externa. Para ello, puede seleccionar la casilla **La dirección IP externa de este grupo de servidores perimetrales se traduce con NAT**. Haga clic en **Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activa la casilla de verificación **usar una dirección IP y FQDN único** , debe escribir el FQDN externo único en el cuadro **Acceso SIP** . A continuación, deberá escribir los números de puerto diferente para cada servicio perimetral para permitir que todos ellos para conectarse de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla de verificación **usar una única dirección IP y FQDN** , ahora deberá escribir el FQDN externos tres para el servicio perimetral de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio perimetral. Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora ha llegado la pantalla **definir los equipos de este grupo de servidores** . Haga clic en el botón **Agregar** .
    
11. Ahora está en la pantalla de **definir la dirección IP interna** . Aquí se tendrá que escribir la dirección IP del servidor perimetral en los cuadros de texto **dirección IPv4 interna** y la **dirección IPv6 interno** , según las opciones seleccionadas en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
12. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (lo que está usando) en el cuadro de texto de **Acceso SIP** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio perimetral y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear se debe aparecer ahora en el cuadro de diálogo **definir los equipos de este grupo de servidores** .
    
14. Mientras sigue en la pantalla **definir los equipos de este grupo de servidores** , haga clic en el botón **Agregar** nuevo y repita los pasos 11 a 13 hasta que haya agregado todos los servidores perimetrales que desee tener en este grupo de servidores. Cuando acabe, haga clic en **Siguiente**.
    
15. Si opta por utilizar NAT en el paso 8, ahora aparecerá una pantalla con un cuadro de texto **dirección IP pública** . Debe escribir la dirección IPv4 o IPv6 pública ha establecido para el / servicio perimetral A/v, que se debe traducir por NAT. Luego, haga clic en **Siguiente**.
    
16. La siguiente pantalla es **Definir el próximo salto**. En el cuadro de **grupo del próximo salto** , seleccione el nombre de su grupo de servidores interno, es posible que un grupo de servidores Front-End o un grupo de servidores independientes. Si tiene un Director en su entorno, debe elegir el Director. Then click **Next**.
    
17. En la pantalla **grupos asociar Front-End** , debe especificar uno o varios grupos de servidores internos, incluidos los grupos de servidores Front-End y los grupos de servidores Standard Edition, para asociar con este servidor perimetral. Sólo tiene que elegir los nombres de los grupos de servidores internos que desea usar este servidor perimetral para comunicarse con usuarios externos admitidos. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo a tener en cuenta aquí es, si los servidores de independientes o grupos de servidores internos utilizan ya un Skype diferente para el servidor perimetral de Business Server, no pueden tener varias asociaciones. Si elige un grupo de servidores interno o un servidor independiente que se encuentra en esa situación, verá aparecer una advertencia de error que informa sobre el otro servidor perimetral, y puede decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
18. Haga clic en **Finalizar** en la pantalla siguiente.
    
19. Ahora podrá publicar esta tecnología actualizada y siga las instrucciones de [Implementación de servidores perimetrales en Skype para Business Server](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definición de la topología para una carga de hardware equilibrada con el grupo de servidores perimetrales

1. Inicie sesión en su Skype para Business Server Standard Edition o un Skype para Business Server Front-End Server.
    
2. Una vez allí, abra **Skype para Business Server Topology Builder**.
    
3. En el árbol de consola, expanda el sitio que va a implementar el servidor perimetral a.
    
4. Haga clic en **grupos de servidores perimetrales**y, a continuación, haga clic en **grupo de servidores perimetrales de nuevo**.
    
5. Aquí clic en **siguiente** en la pantalla de **grupo de servidores perimetrales nueva definir** .
    
6. En la pantalla **definir el FQDN del grupo de servidores perimetrales** , escriba el nombre de dominio completo (FQDN) interno que el grupo de servidores perimetrales se va a usar y, seleccione **el grupo de servidores de varios equipos**, al hacer clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
   - Desea usar la misma dirección IP y FQDN para su servicio de acceso SIP, su Skype Business Server Web servicio de conferencia y su / servicio perimetral A/v. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
   - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estos son bastante fácil de entender, si está utilizando las direcciones IPv4 o IPv6, y va a aplicar esas direcciones en el servidor perimetral interna o externamente (que necesitará para tener en cuenta para el paso 11).
    
     > [!NOTE]
     > A diferencia de las otras dos opciones de topologías, cuando se utiliza un equilibrador de carga de hardware, **No debe** seleccionar la opción **NAT traduce la dirección IP externa del grupo de servidores perimetrales**. **No es compatible**.
  
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activa la casilla de verificación **usar una dirección IP y FQDN único** , debe escribir el FQDN externo único en el cuadro **Acceso SIP** . A continuación, deberá escribir los números de puerto diferente para cada servicio perimetral para permitir que todos ellos para conectarse de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla de verificación **usar una única dirección IP y FQDN** , ahora deberá escribir el FQDN externos tres para el servicio perimetral de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio perimetral. Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora ha llegado la pantalla **definir los equipos de este grupo de servidores** . Haga clic en el botón **Agregar** .
    
11. Ahora está en la pantalla de **definir la dirección IP interna** . Aquí se tendrá que escribir la dirección IP del servidor perimetral en los cuadros de texto **dirección IPv4 interna** y la **dirección IPv6 interno** , según las opciones seleccionadas en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
12. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (lo que está usando) en el cuadro de texto de **Acceso SIP** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio perimetral y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear se debe aparecer ahora en el cuadro de diálogo **definir los equipos de este grupo de servidores** .
    
14. Mientras sigue en la pantalla **definir los equipos de este grupo de servidores** , haga clic en el botón **Agregar** nuevo y repita los pasos 11 a 13 hasta que haya agregado todos los servidores perimetrales que desee tener en este grupo de servidores. Cuando acabe, haga clic en **Siguiente**.
    
15. La siguiente pantalla es **Definir el próximo salto**. En el cuadro de **grupo del próximo salto** , seleccione el nombre de su grupo de servidores interno, es posible que un grupo de servidores Front-End o un grupo de servidores independientes. Si tiene un Director en su entorno, debe elegir el Director. Then click **Next**.
    
16. En la pantalla **grupos asociar Front-End** , debe especificar uno o varios grupos de servidores internos, incluidos los grupos de servidores Front-End y los grupos de servidores Standard Edition, para asociar con este servidor perimetral. Sólo tiene que elegir los nombres de los grupos de servidores internos que desea usar este servidor perimetral para comunicarse con usuarios externos admitidos. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo a tener en cuenta aquí es, si los servidores de independientes o grupos de servidores internos utilizan ya un Skype diferente para el servidor perimetral de Business Server, no pueden tener varias asociaciones. Si elige un grupo de servidores interno o un servidor independiente que se encuentra en esa situación, verá aparecer una advertencia de error que informa sobre el otro servidor perimetral, y puede decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
17. Haga clic en **Finalizar** en la pantalla siguiente.
    
18. Ahora podrá publicar esta tecnología actualizada y siga las instrucciones de [Implementación de servidores perimetrales en Skype para Business Server](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
## <a name="publish-your-edge-server-topology"></a>Publicar la topología del servidor perimetral

Una vez que haya finalizado los pasos anteriores, es el momento de publicar esta nueva topología, que también le permitirá exportar a su Skype para servidor perimetral de Business Server o grupo perimetral. Siga estos pasos:
  
1. Inicie el **Generador de topologías** (si no se ha iniciado ya en el procedimiento anterior).
    
2. En el **Generador de topologías**, en el árbol de consola, secundario **Skype para Business Server** y, a continuación, haga clic en **Skype para Business Server Topology Builder**.
    
3. En la página **principal** del asistente, haga clic en **Siguiente**.
    
4. En la página **Crear otras bases de datos**, haga clic en **Siguiente**.
    
5. Cuando el estado indica que la creación de bases de datos se ha realizado correctamente, haga lo siguiente:
    
    - Para visualizar el registro, haga clic en **Ver registro**.
    
    - Para cerrar el asistente, haga clic en **Finalizar**.
    
## <a name="export-your-edge-server-topology"></a>Exportar la topología del servidor perimetral

Para implementar correctamente, el Skype para el Asistente para implementación de servidor empresarial necesita tener acceso a los datos del almacén de Administración Central. Para los servidores internos de su dominio o bosque, por lo general, es un proceso sencillo. Los servidores perimetrales están fuera del dominio y, por lo que es necesario exportar manualmente el archivo de topología a la ubicación del servidor perimetral, normalmente en un medio físico. Esta exportación se realiza con PowerShell:
  
1. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
2. En el **Skype para Business Server Management Shell**, ejecute lo siguiente:
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie el archivo exportado a medios externos (por ejemplo, un USB unidad o recurso compartido que puede tener acceso desde la ubicación del servidor perimetral).
    

