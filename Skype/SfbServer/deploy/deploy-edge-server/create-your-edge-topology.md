---
title: Crear la topología perimetral para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumen: Aprender a crear, publicar y exportar la topología de servidor perimetral de Skype para Business Server 2015.'
ms.openlocfilehash: 336bef93fbb0d58c07ebd845fff2751e85464900
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-your-edge-topology-for-skype-for-business-server-2015"></a>Crear la topología perimetral para Skype Empresarial Server 2015
 
**Resumen:** Aprenda a crear, publicar y exportar la topología de servidor perimetral de Skype para Business Server 2015.
  
El generador de topología es la herramienta que se debe utilizar para generar la topología de servidor perimetral, tal como se utiliza para cualquier componente de la topología de Skype para Business Server 2015. Antes de seguir los pasos siguientes, debe haber configurado al menos un grupo de servidores Front-End o un servidor Standard Edition.
  
Se tratarán los siguientes temas en este artículo:
  
- Generar la topología de servidor perimetral
    
- Publicar la topología del servidor perimetral
    
- Exportar la topología del servidor perimetral
    
  > [!NOTE]
  > Para seguir los pasos que se indican a continuación, tendrá que iniciar sesión en los servidores del dominio mencionados a continuación como un usuario que es miembro de los siguientes grupos de dominio: 
  
- RTCUniversalServerAdmins
    
- Administradores de dominio
    
## <a name="build-your-edge-server-topology"></a>Generar la topología de servidor perimetral

El primer paso de implementación está creando su Skype para la topología de servidor perimetral de Business Server 2015, que consiste en una de tres opciones:
  
- Un único servidor de borde
    
- Un grupo de borde de carga equilibrada de DNS (uno o varios servidores)
    
- Un hardware equilibran la piscina de borde (uno o varios servidores)
    
Si no está seguro de qué necesita, siga estos pasos antes de empezar, es un buen momento para ver la documentación de la planeación. De lo contrario, comencemos.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definir la topología de un único servidor de borde

1. Inicie sesión en su Skype para servidor de 2015 Business Server Standard Edition o un Skype para el grupo de servidores Front-End de Business Server 2015.
    
2. Una vez allí, abra **Skype para el generador de topología de Business Server 2015**.
    
3. En el árbol de consola, expanda el sitio que se va a implementar el servidor Edge.
    
4. Haga clic derecho en **grupos de borde**y, a continuación, haga clic en **grupo nuevo borde**.
    
5. Se le haga clic en **siguiente** en la pantalla **definir borde nuevo grupo** .
    
6. En la pantalla **definir el FQDN del grupo de borde** , escriba el nombre de dominio completo (FQDN) interno que va a utilizar el servidor perimetral y seleccione el **grupo de equipo único**, haga clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
   - Piensa utilizar la misma dirección IP y FQDN para el servicio de acceso SIP, su Skype para el servicio de conferencias Web de Business Server 2015 y su / servicio V perimetral. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
   - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
   Estas son bastante descriptivos, si está utilizando direcciones IPv4 o IPv6, y va a aplicar esas direcciones en el servidor perimetral interna o externamente (deberá tener en cuenta para el paso 10). También tiene la opción de configurar su servidor perimetral o la piscina de borde para utilizar una dirección de traducción (NAT) de dirección de red para la dirección IP externa. Para ello, puede seleccionar la casilla **La dirección IP externa de este grupo de servidores perimetrales se traduce con NAT**. Haga clic en **Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activa la casilla de verificación **usar una dirección IP y FQDN único** , debe especificar el FQDN externo solo en el cuadro **Acceso SIP** . A continuación, debe introducir los números de puerto diferentes para cada servicio de borde para permitir que todos ellos para conectarse de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla de verificación **utilizar una única dirección IP y FQDN** , ahora debe especificar el FQDN externos tres para el servicio de borde de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio de borde. Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora está en la pantalla **definir la dirección IP interna** . Aquí usted tendrá que escribir la dirección IP de su servidor de borde en los cuadros de texto de **dirección IPv4 internas** y **dirección IPv6 interno** , según las opciones seleccionadas en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
11. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (lo que está utilizando) en el cuadro de texto de **Acceso SIP** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba las direcciones de IPv4 o IPv6 externas para el servicio de borde de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio de borde y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
12. Si decide utilizar NAT en el paso 8, ahora obtendrá una pantalla con un cuadro de texto **dirección IP pública** . Tendrá que introducir la dirección IPv4 o IPv6 pública establecidas en lugar de A / servicio de borde V, ser traducidos por NAT. Luego, haga clic en **Siguiente**.
    
13. La siguiente pantalla es **Definir el próximo salto**. En el cuadro **grupo de salto siguiente** , seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores Front-End o un grupo independiente. Si tienes un Director en su entorno, debe elegir el Director. Then click **Next**.
    
14. En la pantalla de **grupos asociar Front-End** , debe especificar uno o más grupos internos, incluidos grupos de Front-End y servidores Standard Edition, para asociar con este servidor perimetral. Sólo tiene que elegir los nombres de los grupos internos que desee utilizar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo a tener en cuenta es si los grupos internos o servidores independientes utilizan ya una Skype diferente para el servidor perimetral de Business Server 2015, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, verá aparecer una advertencia de informarle acerca de otro servidor de borde y puede decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
15. Haga clic en **Finalizar** en la pantalla siguiente.
    
16. Ahora podrá publicar esta tecnología actualizada y siga las instrucciones de [Implementar servidores perimetrales en Skype para Business Server 2015](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definir la topología de un DNS grupo servidor perimetral con equilibrio de carga

1. Inicie sesión en su Skype para servidor de 2015 Business Server Standard Edition o un Skype para servidor Front-End de Business Server 2015.
    
2. Una vez allí, abra **Skype para el generador de topología de Business Server 2015**.
    
3. En el árbol de consola, expanda el sitio que se va a implementar el servidor Edge.
    
4. Haga clic derecho en **grupos de borde**y, a continuación, haga clic en **grupo nuevo borde**.
    
5. Se le haga clic en **siguiente** en la pantalla **definir borde nuevo grupo** .
    
6. En la pantalla **definir el FQDN del grupo de borde** , escriba el nombre de dominio completo (FQDN) interno que va a utilizar la piscina de borde y seleccione **varios grupo de equipo**, haga clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
    - Piensa utilizar la misma dirección IP y FQDN para el servicio de acceso SIP, su Skype para el servicio de conferencias Web de Business Server 2015 y su / servicio V perimetral. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
    - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
    - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
    Estas son bastante descriptivos, si está utilizando direcciones IPv4 o IPv6, y va a aplicar esas direcciones en el servidor perimetral interna o externamente (deberá tener en cuenta para el paso 11). También tiene la opción de configurar su servidor perimetral o la piscina de borde para utilizar una dirección de traducción (NAT) de dirección de red para la dirección IP externa. Para ello, puede seleccionar la casilla **La dirección IP externa de este grupo de servidores perimetrales se traduce con NAT**. Haga clic en **Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activa la casilla de verificación **usar una dirección IP y FQDN único** , debe especificar el FQDN externo solo en el cuadro **Acceso SIP** . A continuación, debe introducir los números de puerto diferentes para cada servicio de borde para permitir que todos ellos para conectarse de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla de verificación **utilizar una única dirección IP y FQDN** , ahora debe especificar el FQDN externos tres para el servicio de borde de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio de borde. Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora ha llegado la pantalla **definir los equipos de este grupo** . Haga clic en el botón **Agregar** .
    
11. Ahora está en la pantalla **definir la dirección IP interna** . Aquí usted tendrá que escribir la dirección IP de su servidor de borde en los cuadros de texto de **dirección IPv4 internas** y **dirección IPv6 interno** , según las opciones seleccionadas en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
12. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (lo que está utilizando) en el cuadro de texto de **Acceso SIP** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba las direcciones de IPv4 o IPv6 externas para el servicio de borde de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio de borde y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer ahora en el cuadro de diálogo **definir los equipos de este grupo** .
    
14. Mientras sigue en la pantalla **definir los equipos de este grupo** , haga clic en el botón **Agregar** nuevo y repita los pasos 11 a 13 hasta que haya agregado todos los servidores de borde que desee tener en este grupo. Cuando acabe, haga clic en **Siguiente**.
    
15. Si decide utilizar NAT en el paso 8, ahora obtendrá una pantalla con un cuadro de texto **dirección IP pública** . Tendrá que introducir la dirección IPv4 o IPv6 pública establecidas en lugar de A / servicio de borde V, ser traducidos por NAT. Luego, haga clic en **Siguiente**.
    
16. La siguiente pantalla es **Definir el próximo salto**. En el cuadro **grupo de salto siguiente** , seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores Front-End o un grupo independiente. Si tienes un Director en su entorno, debe elegir el Director. Then click **Next**.
    
17. En la pantalla de **grupos asociar Front-End** , debe especificar uno o más grupos internos, incluidas las agrupaciones de Front-End y las agrupaciones de Standard Edition, para asociar con este servidor perimetral. Sólo tiene que elegir los nombres de los grupos internos que desee utilizar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo a tener en cuenta es si los grupos internos o servidores independientes utilizan ya una Skype diferente para el servidor perimetral de Business Server 2015, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, verá aparecer una advertencia de informarle acerca de otro servidor de borde y puede decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
18. Haga clic en **Finalizar** en la pantalla siguiente.
    
19. Ahora podrá publicar esta tecnología actualizada y siga las instrucciones de [Implementar servidores perimetrales en Skype para Business Server 2015](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definir la topología para una carga de hardware equilibrado grupo servidor perimetral

1. Inicie sesión en su Skype para servidor de 2015 Business Server Standard Edition o un Skype para servidor Front-End de Business Server 2015.
    
2. Una vez allí, abra **Skype para el generador de topología de Business Server 2015**.
    
3. En el árbol de consola, expanda el sitio que se va a implementar el servidor Edge.
    
4. Haga clic derecho en **grupos de borde**y, a continuación, haga clic en **grupo nuevo borde**.
    
5. Se le haga clic en **siguiente** en la pantalla **definir borde nuevo grupo** .
    
6. En la pantalla **definir el FQDN del grupo de borde** , escriba el nombre de dominio completo (FQDN) interno que va a utilizar la piscina de borde y seleccione **varios grupo de equipo**, haga clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
   - Piensa utilizar la misma dirección IP y FQDN para el servicio de acceso SIP, su Skype para el servicio de conferencias Web de Business Server 2015 y su / servicio V perimetral. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
   - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
    Estas son bastante descriptivos, si está utilizando direcciones IPv4 o IPv6, y va a aplicar esas direcciones en el servidor perimetral interna o externamente (deberá tener en cuenta para el paso 11).
    
    > [!NOTE]
    > A diferencia de las otras dos opciones de topología, cuando se utiliza un equilibrador de carga de hardware, **No debe** seleccionar la opción **NAT traduce la dirección IP externa de la piscina de borde**. **No es compatible**.
  
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activa la casilla de verificación **usar una dirección IP y FQDN único** , debe especificar el FQDN externo solo en el cuadro **Acceso SIP** . A continuación, debe introducir los números de puerto diferentes para cada servicio de borde para permitir que todos ellos para conectarse de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla de verificación **utilizar una única dirección IP y FQDN** , ahora debe especificar el FQDN externos tres para el servicio de borde de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio de borde. Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora ha llegado la pantalla **definir los equipos de este grupo** . Haga clic en el botón **Agregar** .
    
11. Ahora está en la pantalla **definir la dirección IP interna** . Aquí usted tendrá que escribir la dirección IP de su servidor de borde en los cuadros de texto de **dirección IPv4 internas** y **dirección IPv6 interno** , según las opciones seleccionadas en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
12. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (lo que está utilizando) en el cuadro de texto de **Acceso SIP** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba las direcciones de IPv4 o IPv6 externas para el servicio de borde de **Acceso SIP** , el servicio perimetral de **Conferencia Web** y la **A / V** servicio de borde y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer ahora en el cuadro de diálogo **definir los equipos de este grupo** .
    
14. Mientras sigue en la pantalla **definir los equipos de este grupo** , haga clic en el botón **Agregar** nuevo y repita los pasos 11 a 13 hasta que haya agregado todos los servidores de borde que desee tener en este grupo. Cuando acabe, haga clic en **Siguiente**.
    
15. La siguiente pantalla es **Definir el próximo salto**. En el cuadro **grupo de salto siguiente** , seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores Front-End o un grupo independiente. Si tienes un Director en su entorno, debe elegir el Director. Then click **Next**.
    
16. En la pantalla de **grupos asociar Front-End** , debe especificar uno o más grupos internos, incluidas las agrupaciones de Front-End y las agrupaciones de Standard Edition, para asociar con este servidor perimetral. Sólo tiene que elegir los nombres de los grupos internos que desee utilizar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo a tener en cuenta es si los grupos internos o servidores independientes utilizan ya una Skype diferente para el servidor perimetral de Business Server 2015, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, verá aparecer una advertencia de informarle acerca de otro servidor de borde y puede decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
17. Haga clic en **Finalizar** en la pantalla siguiente.
    
18. Ahora podrá publicar esta tecnología actualizada y siga las instrucciones de [Implementar servidores perimetrales en Skype para Business Server 2015](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
## <a name="publish-your-edge-server-topology"></a>Publicar la topología del servidor perimetral

Una vez que haya terminado los pasos anteriores, es el momento de publicar esta nueva topología, que también le permitirá exportarlo a tu Skype para grupo Business Server 2015 Edge Server o arista. Siga estos pasos:
  
1. Inicie el **Generador de topologías** (si no se ha iniciado ya en el procedimiento anterior).
    
2. En el **Generador de topología**, en el árbol de consola, haga **Skype para Business Server 2015** y, a continuación, haga clic en **Skype para el generador de topología de servidor empresarial**.
    
3. En la página **principal** del asistente, haga clic en **Siguiente**.
    
4. En la página **Crear otras bases de datos**, haga clic en **Siguiente**.
    
5. Cuando el estado indica que la creación de bases de datos se ha realizado correctamente, haga lo siguiente:
    
    - Para visualizar el registro, haga clic en **Ver registro**.
    
    - Para cerrar el asistente, haga clic en **Finalizar**.
    
## <a name="export-your-edge-server-topology"></a>Exportar la topología del servidor perimetral

Para implementar con éxito, el Skype para el Asistente para implementación de Business Server 2015 necesita acceso a los datos del almacén de Administración Central. Para los servidores internos de su dominio o bosque, por lo general, es un proceso sencillo. Servidores perimetrales están fuera del dominio y, por lo que es necesario exportar manualmente el archivo de topología a la ubicación del servidor de borde, normalmente en un medio físico. Esta exportación se realiza con PowerShell:
  
1. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
2. En el **Skype para negocios de Shell de administración de servidor**, ejecute lo siguiente:
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie el archivo exportado a medios externos (por ejemplo, un USB unidad o recurso compartido que se puede llegar desde la ubicación del servidor de borde).
    

