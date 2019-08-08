---
title: Crear la topología perimetral para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumen: Aprenda a crear, publicar y exportar la topología del servidor perimetral en Skype empresarial Server.'
ms.openlocfilehash: b20877f805cb0357f6038a822962ad6eb9cdd5e1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233910"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Crear la topología perimetral para Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear, publicar y exportar la topología del servidor perimetral en Skype empresarial Server.
  
El generador de topología es la herramienta que necesita usar para crear la topología de servidores perimetrales, tal y como se usa para cualquier componente de topología de Skype empresarial Server. Antes de seguir los pasos que se indican a continuación, debe haber configurado al menos un grupo de servidores front-end o un servidor Standard Edition.
  
Se tratarán los siguientes temas en este artículo:
  
- Crear la topología de su servidor perimetral
    
- Publicar la topología del servidor perimetral
    
- Exportar la topología del servidor perimetral
    
  > [!NOTE]
  > Para seguir los pasos que se indican a continuación, tendrá que iniciar sesión en los servidores del dominio mencionados a continuación como un usuario que es miembro de los siguientes grupos de dominio: 
  
- RTCUniversalServerAdmins
    
- Administradores de dominio
    
## <a name="build-your-edge-server-topology"></a>Crear la topología de su servidor perimetral

El primer paso de implementación es la creación de la topología de servidor perimetral de Skype empresarial Server, que consta de una de las tres opciones siguientes:
  
- Un único servidor perimetral
    
- Un grupo perimetral con equilibrio de carga DNS (uno o más servidores)
    
- Un grupo de perímetro equilibrado de carga de hardware (uno o varios servidores)
    
Si no está seguro de qué necesita, siga estos pasos antes de empezar, es un buen momento para ver la documentación de la planeación. De lo contrario, comencemos.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definir la topología para un único servidor perimetral

1. Inicie sesión en su servidor de Skype empresarial Server Standard Edition o en un grupo de servidores front-end de Skype empresarial Server.
    
2. Una vez allí, abra el **generador de topologías de Skype empresarial Server**.
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con **** el botón secundario en agrupaciones perimetrales y luego haga clic en **nuevo borde**.
    
5. En la pantalla **definir nuevo borde** , haga clic en **siguiente** .
    
6. En la pantalla **definir el FQDN del grupo perimetral** , escriba el nombre de dominio completo interno (FQDN) que el servidor perimetral va a usar y seleccione **grupo de equipos único**y haga clic en **siguiente** cuando termine.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
   - Es posible que desee usar el mismo FQDN e dirección IP para su servicio de acceso SIP, su servicio de conferencias web de Skype empresarial Server y su servicio perimetral A/V. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
   - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
   Estas son bastante claras, ya sea que use direcciones IPv4 o IPv6, y las está aplicando en el servidor perimetral de forma interna o externa (tendrá que tener esto en cuenta para el paso 10). También tiene la opción de configurar el servidor perimetral o el grupo de servidores perimetrales para que use una dirección de traducción de direcciones de red (NAT) para la dirección IP externa. Para ello, puede seleccionar la casilla **La dirección IP externa de este grupo de servidores perimetrales se traduce con NAT**. Haga clic en **Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activó la casilla **usar un solo FQDN e dirección IP** , tendrá que escribir su único FQDN externo en el cuadro de **acceso SIP** . A continuación, tendrás que introducir números de puertos diferentes para cada servicio perimetral y permitir que todos se conecten de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla **usar un solo FQDN e dirección IP** , tendrá que introducir los tres FQDN externos para el servicio perimetral de **acceso SIP** , el servicio perimetral de **conferencias web** y el servicio perimetral **a/V** . Haga clic en **Siguiente** cuando haya acabado.
    
10. Ahora está en la pantalla **definir la dirección IP interna** . Aquí, escriba la dirección IP de su servidor perimetral en los cuadros de texto dirección **IPv4 interna** y **dirección IPv6 interna** , según las elecciones que haya elegido en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
11. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba su dirección IPv4 o IPv6 externa (la que esté usando) en el cuadro de texto **SIP Access** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba sus direcciones IPv4 o IPv6 externas para el servicio perimetral de **acceso SIP** , el servicio perimetral de **conferencias web** y el servicio perimetral a **/V** y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
12. Si decides usar NAT en el paso 8, ahora disfrutarás de una pantalla con un cuadro de texto de **dirección IP pública** . Tendrá que introducir la dirección IPv4 y/o IPv6 pública que haya establecido para el servicio perimetral a/V, que se traducirá por NAT. Luego, haga clic en **Siguiente**.
    
13. La siguiente pantalla es **Definir el próximo salto**. En el cuadro **grupo de próximos saltos** , seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. Then click **Next**.
    
14. En la pantalla de las **agrupaciones front end** , tendrá que especificar uno o varios pools internos, entre los que se incluyen grupos de aplicaciones para el usuario y servidores Standard Edition, para asociarlos con este servidor perimetral. Solo tiene que elegir los nombres de los grupos internos que desea que el servidor perimetral se comunique con los usuarios externos admitidos. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Lo que hay que tener en cuenta es que, si los grupos internos o los servidores independientes ya usan un servidor perimetral de Skype empresarial diferente, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, aparecerá una advertencia que le indicará sobre el otro servidor perimetral y podrá decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
15. Haga clic en **Finalizar** en la pantalla siguiente.
    
16. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de [implementar servidores perimetrales en Skype empresarial Server](deploy-edge-servers.md) para desplegar en su servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definir la topología de un grupo de servidores perimetrales de carga equilibrada de DNS

1. Inicie sesión en su servidor de Skype empresarial Server Standard Edition o en un servidor front-end de Skype empresarial Server.
    
2. Una vez allí, abra el **generador de topologías de Skype empresarial Server**.
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con **** el botón secundario en agrupaciones perimetrales y luego haga clic en **nuevo borde**.
    
5. En la pantalla **definir nuevo borde** , haga clic en **siguiente** .
    
6. En la pantalla **definir el FQDN del grupo perimetral** , escriba el nombre de dominio completo interno (FQDN) que el grupo de servidores perimetrales va a usar y seleccione **varios grupos de equipos**y haga clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
    - Es posible que desee usar el mismo FQDN e dirección IP para su servicio de acceso SIP, su servicio de conferencias web de Skype empresarial Server y su servicio perimetral A/V. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
    - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
    - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estas son bastante claras, ya sea que use direcciones IPv4 o IPv6, y las está aplicando en el servidor perimetral de forma interna o externa (tendrá que tener esto en cuenta para el paso 11). También tiene la opción de configurar el servidor perimetral o el grupo de servidores perimetrales para que use una dirección de traducción de direcciones de red (NAT) para la dirección IP externa. Para ello, puede seleccionar la casilla **La dirección IP externa de este grupo de servidores perimetrales se traduce con NAT**. Haga clic en **Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activó la casilla **usar un solo FQDN e dirección IP** , tendrá que escribir su único FQDN externo en el cuadro de **acceso SIP** . A continuación, tendrás que introducir números de puertos diferentes para cada servicio perimetral y permitir que todos se conecten de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla **usar un solo FQDN e dirección IP** , tendrá que introducir los tres FQDN externos para el servicio perimetral de **acceso SIP** , el servicio perimetral de **conferencias web** y el servicio perimetral **a/V** . Haga clic en **Siguiente** cuando haya acabado.
    
10. Ya ha llegado a la pantalla **definir los equipos de este grupo** . Haga clic en el botón **Agregar** .
    
11. Ahora está en la pantalla **definir la dirección IP interna** . Aquí, escriba la dirección IP de su servidor perimetral en los cuadros de texto dirección **IPv4 interna** y **dirección IPv6 interna** , según las elecciones que haya elegido en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
12. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba su dirección IPv4 o IPv6 externa (la que esté usando) en el cuadro de texto **SIP Access** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba sus direcciones IPv4 o IPv6 externas para el servicio perimetral de **acceso SIP** , el servicio perimetral de **conferencias web** y el servicio perimetral a **/V** y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer en el cuadro de diálogo **definir los equipos de este grupo** .
    
14. Mientras se encuentre en la pantalla **definir los equipos de este grupo** , vuelva a hacer clic en el botón **Agregar** y repita los pasos 11 a 13 hasta que haya agregado todos los servidores perimetrales que desea tener en este grupo. Cuando acabe, haga clic en **Siguiente**.
    
15. Si decides usar NAT en el paso 8, ahora disfrutarás de una pantalla con un cuadro de texto de **dirección IP pública** . Tendrá que introducir la dirección IPv4 y/o IPv6 pública que haya establecido para el servicio perimetral a/V, que se traducirá por NAT. Luego, haga clic en **Siguiente**.
    
16. La siguiente pantalla es **Definir el próximo salto**. En el cuadro **grupo de próximos saltos** , seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. Then click **Next**.
    
17. En la pantalla de las **agrupaciones front end** , tendrá que especificar uno o varios pools internos, incluidos los grupos de aplicaciones para el usuario y los grupos de Standard Edition, para asociarlos con este servidor perimetral. Solo tiene que elegir los nombres de los grupos internos que desea que el servidor perimetral se comunique con los usuarios externos admitidos. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Lo que hay que tener en cuenta es que, si los grupos internos o los servidores independientes ya usan un servidor perimetral de Skype empresarial diferente, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, aparecerá una advertencia que le indicará sobre el otro servidor perimetral y podrá decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
18. Haga clic en **Finalizar** en la pantalla siguiente.
    
19. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de [implementar servidores perimetrales en Skype empresarial Server](deploy-edge-servers.md) para desplegar en su servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

1. Inicie sesión en su servidor de Skype empresarial Server Standard Edition o en un servidor front-end de Skype empresarial Server.
    
2. Una vez allí, abra el **generador de topologías de Skype empresarial Server**.
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con **** el botón secundario en agrupaciones perimetrales y luego haga clic en **nuevo borde**.
    
5. En la pantalla **definir nuevo borde** , haga clic en **siguiente** .
    
6. En la pantalla **definir el FQDN del grupo perimetral** , escriba el nombre de dominio completo interno (FQDN) que el grupo de servidores perimetrales va a usar y seleccione **varios grupos de equipos**y haga clic en **siguiente** cuando haya terminado.
    
7. En la pantalla **Seleccionar características**, puede elegir:
    
   - Es posible que desee usar el mismo FQDN e dirección IP para su servicio de acceso SIP, su servicio de conferencias web de Skype empresarial Server y su servicio perimetral A/V. Si es así, tiene que seleccionar la casilla **Usar un solo FQDN y una dirección IP** (y recuerde esto para el paso 9)
    
   - Si está pensando en habilitar la federación, seleccione la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.
    
8. Una vez que haya hecho clic en **Siguiente**, se encontrará en la pantalla **Opciones de IP**. Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estas son bastante claras, ya sea que use direcciones IPv4 o IPv6, y las está aplicando en el servidor perimetral de forma interna o externa (tendrá que tener esto en cuenta para el paso 11).
    
     > [!NOTE]
     > A diferencia de las otras dos opciones de topología, al usar un equilibrador de carga de hardware, **no debe** seleccionar la opción en la que **NAT traduce la dirección IP externa del grupo Edge**. **No es compatible**.
  
9. En la pantalla FQDN externos, las opciones dependen de la selección que hizo en el paso 7.
    
   - Si activó la casilla **usar un solo FQDN e dirección IP** , tendrá que escribir su único FQDN externo en el cuadro de **acceso SIP** . A continuación, tendrás que introducir números de puertos diferentes para cada servicio perimetral y permitir que todos se conecten de forma independiente. Le recomendamos 5061 para el servicio perimetral **Acceso SIP**, 444 para el servicio perimetral **Conferencia web** y 443 para el servicio perimetral **A/V**. Haga clic en **Siguiente** cuando haya acabado.
    
   - Si no activó la casilla **usar un solo FQDN e dirección IP** , tendrá que introducir los tres FQDN externos para el servicio perimetral de **acceso SIP** , el servicio perimetral de **conferencias web** y el servicio perimetral **a/V** . Haga clic en **Siguiente** cuando haya acabado.
    
10. Ya ha llegado a la pantalla **definir los equipos de este grupo** . Haga clic en el botón **Agregar** .
    
11. Ahora está en la pantalla **definir la dirección IP interna** . Aquí, escriba la dirección IP de su servidor perimetral en los cuadros de texto dirección **IPv4 interna** y **dirección IPv6 interna** , según las elecciones que haya elegido en el paso 8. Haga clic en **Siguiente** cuando esté listo.
    
12. En la pantalla **Definir la dirección IP externa**, tiene algunas opciones en función de las elecciones anteriores:
    
    - Puede que esté usando un FQDN único para todos los servicios. Si es así, escriba su dirección IPv4 o IPv6 externa (la que esté usando) en el cuadro de texto **SIP Access** y, a continuación, haga clic en **siguiente**.
    
    - Puede que haya decidido usar tres FQDN y direcciones IP diferentes para los servicios. Si ese es el caso, escriba sus direcciones IPv4 o IPv6 externas para el servicio perimetral de **acceso SIP** , el servicio perimetral de **conferencias web** y el servicio perimetral a **/V** y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Si no optó por habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Es normal, vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer en el cuadro de diálogo **definir los equipos de este grupo** .
    
14. Mientras se encuentre en la pantalla **definir los equipos de este grupo** , vuelva a hacer clic en el botón **Agregar** y repita los pasos 11 a 13 hasta que haya agregado todos los servidores perimetrales que desea tener en este grupo. Cuando acabe, haga clic en **Siguiente**.
    
15. La siguiente pantalla es **Definir el próximo salto**. En el cuadro **grupo de próximos saltos** , seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. Then click **Next**.
    
16. En la pantalla de las **agrupaciones front end** , tendrá que especificar uno o varios pools internos, incluidos los grupos de aplicaciones para el usuario y los grupos de Standard Edition, para asociarlos con este servidor perimetral. Solo tiene que elegir los nombres de los grupos internos que desea que el servidor perimetral se comunique con los usuarios externos admitidos. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Lo que hay que tener en cuenta es que, si los grupos internos o los servidores independientes ya usan un servidor perimetral de Skype empresarial diferente, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, aparecerá una advertencia que le indicará sobre el otro servidor perimetral y podrá decidir si desea continuar o no. Si sigue adelante con la nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
17. Haga clic en **Finalizar** en la pantalla siguiente.
    
18. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de [implementar servidores perimetrales en Skype empresarial Server](deploy-edge-servers.md) para desplegar en su servidor perimetral desde aquí.
    
## <a name="publish-your-edge-server-topology"></a>Publicar la topología del servidor perimetral

Una vez que haya terminado los pasos anteriores, es el momento de publicar esta nueva topología, que también le permitirá exportarla a su servidor perimetral de Skype empresarial Server o al grupo Edge. Siga estos pasos:
  
1. Inicie el **Generador de topologías** (si no se ha iniciado ya en el procedimiento anterior).
    
2. En el **generador de topología**, en el árbol de consola, haga clic con el botón secundario en **Skype empresarial Server** y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.
    
3. En la página **principal** del asistente, haga clic en **Siguiente**.
    
4. En la página **Crear otras bases de datos**, haga clic en **Siguiente**.
    
5. Cuando el estado indica que la creación de bases de datos se ha realizado correctamente, haga lo siguiente:
    
    - Para visualizar el registro, haga clic en **Ver registro**.
    
    - Para cerrar el asistente, haga clic en **Finalizar**.
    
## <a name="export-your-edge-server-topology"></a>Exportar la topología del servidor perimetral

Para que se implemente correctamente, el Asistente para la implementación de Skype empresarial Server necesita acceso a los datos del almacén central de administración. Para los servidores internos de su dominio o bosque, por lo general, es un proceso sencillo. Los servidores perimetrales están fuera del dominio y, por lo tanto, es necesario exportar manualmente el archivo de topología a la ubicación del servidor perimetral, generalmente en un medio físico. Esta exportación se realiza con PowerShell:
  
1. Inicie el **Shell de administración de Skype empresarial Server**.
    
2. En el **Shell de administración de Skype empresarial Server**, ejecute lo siguiente:
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie el archivo exportado a un medio externo (por ejemplo, una unidad USB o un recurso compartido de red al que pueda tener acceso desde la ubicación del servidor perimetral).
    

