---
title: Crear la topología perimetral para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumen: obtenga información sobre cómo crear, publicar y exportar la topología del servidor perimetral en Skype Empresarial Server.'
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804400"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Crear la topología perimetral para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear, publicar y exportar la topología del servidor perimetral en Skype Empresarial Server.
  
Topology Builder es la herramienta que necesita usar para crear la topología del servidor perimetral, tal como se usa para cualquier componente de topología para Skype Empresarial Server. Antes de seguir los pasos siguientes, deberá haber configurado al menos un grupo de servidores front-end o un servidor Standard Edition.
  
Tratamos los siguientes temas de este artículo:
  
- Crear la topología del servidor perimetral
    
- Publicar la topología del servidor perimetral
    
- Exportar la topología del servidor perimetral
    
  > [!NOTE]
  > Para seguir los pasos siguientes, tendrá que iniciar sesión en los servidores de dominio mencionados a continuación como un usuario miembro de los siguientes grupos de dominio: 
  
- RTCUniversalServerAdmins
    
- Domain Admins
    
## <a name="build-your-edge-server-topology"></a>Crear la topología del servidor perimetral

El primer paso de implementación consiste en crear la topología del servidor perimetral de Skype Empresarial Server, que consta de una de las tres opciones siguientes:
  
- Un único servidor perimetral
    
- Un grupo de servidores perimetrales con equilibrio de carga DNS (uno o más servidores)
    
- Un grupo de servidores perimetrales con equilibrio de carga de hardware (uno o más servidores)
    
Si no está seguro de lo que necesita, antes de empezar a seguir estos pasos, es un buen momento para ver la documentación de planeación. De lo contrario, empecemos.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definición de la topología para un único servidor perimetral

1. Inicie sesión en el servidor Standard Edition de Skype Empresarial Server o en un grupo de servidores front-end de Skype Empresarial Server.
    
2. Una vez allí, abra el Generador de **topologías de Skype Empresarial Server.**
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con el botón **secundario en Grupos de servidores perimetrales** y, a continuación, haga clic en Nuevo grupo de servidores **perimetrales.**
    
5. Haga clic en **Siguiente en** la pantalla Definir nuevo grupo de **servidores perimetrales.**
    
6. En la pantalla Definir el **FQDN** del grupo de servidores perimetrales, escriba el nombre de dominio completo  (FQDN) interno que va a usar el servidor perimetral y seleccione Grupo de servidores de un solo equipo haciendo clic en Siguiente cuando haya terminado.
    
7. En la **pantalla Seleccionar** características, puede elegir:
    
   - Es posible que tenga la intención de usar el mismo FQDN y dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Skype Empresarial Server y el servicio perimetral A/V. Si es así, debe seleccionar la casilla Usar un **solo FQDN** y dirección IP (y tenga esto en cuenta para el paso 9 a continuación)
    
   - Si tiene previsto habilitar la federación, seleccione la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061).**
    
8. Una vez que haya hecho clic en **Siguiente,** se encontrará en la pantalla **Opciones de IP.** Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
   Estas son bastante fáciles de explicar, tanto si usa direcciones IPv4 o IPv6 como si las está aplicando en el servidor perimetral interna o externamente (tendrá que tener esto en cuenta en el paso 10). También tiene la opción de configurar el servidor perimetral o el grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red (NAT) para la dirección IP externa. Para ello, seleccione la dirección IP externa de este grupo de servidores perimetrales mediante la casilla **NAT.** Haga **clic en Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección realizada en el paso 7 anterior.
    
   - Si ha activado la casilla **Usar un solo FQDN** y una dirección IP, debe escribir el FQDN externo único en el cuadro acceso **SIP.** A continuación, tendrá que escribir números de puerto diferentes para cada servicio perimetral para permitir que todos se conecten de forma independiente. Se recomienda 5061 para el servicio perimetral de acceso **SIP,** 444 para el servicio perimetral de conferencia **web** y 443 para el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
   - Si no ha marcado la casilla Usar un **solo FQDN** y dirección IP, ahora tendrá que escribir los tres FQDN externos para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
10. Ahora está en la pantalla Definir **la dirección IP** interna. Aquí escribirá la dirección IP del servidor perimetral en los cuadros de texto Dirección **IPv4** interna e **IPv6** interna, en función de las elecciones que realizó en el paso 8. Haga **clic en Siguiente** cuando esté listo.
    
11. En la **pantalla Definir la dirección IP externa,** tiene algunas opciones en función de las opciones anteriores:
    
    - Puede que esté usando un solo FQDN para todos los servicios. Si es así, escriba su dirección IPv4 o IPv6 externa (lo que use) en el cuadro de texto **Acceso SIP** y, a continuación, haga clic en **Siguiente**.
    
    - Puede que haya elegido usar tres FQDN y direcciones IP independientes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V** y, a continuación, haga clic en **Siguiente.**
    
    > [!NOTE]
    > Si no ha elegido previamente habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Eso es normal, solo tienes que ir al paso siguiente. 
  
12. Si decidió volver a usar NAT en el paso 8, ahora verá una pantalla con un cuadro de texto **de dirección IP** pública. Deberá escribir la dirección IPv4 o IPv6 pública que haya establecido para el servicio perimetral A/V, para que NAT la traduzca. A continuación, haga clic en **Siguiente**.
    
13. La siguiente pantalla es **Definir el próximo salto.** En el **cuadro Grupo de servidores del** próximo salto, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. A continuación, haga clic en **Siguiente**.
    
14. En la **pantalla** Asociar grupos de servidores front-end, deberá especificar uno o más grupos de servidores internos, incluidos los grupos de servidores front-end y los servidores Standard Edition, para asociar con este servidor perimetral. Solo tiene que elegir los nombres de los grupos de servidores internos que desee usar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo que se debe tener en cuenta aquí es que, si los grupos de servidores internos o los servidores independientes ya usan un servidor perimetral de Skype Empresarial Server diferente, no pueden tener varias asociaciones. Si elige un grupo de servidores interno o un servidor independiente que se encuentra en esa situación, verá una advertencia que le indica sobre el otro servidor perimetral y puede decidir si desea continuar o no. Si continúa con esta nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
15. Haga **clic en Finalizar** en la siguiente pantalla.
    
16. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de Implementar servidores perimetrales en Skype Empresarial [Server](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definición de la topología para un grupo de servidores perimetrales con equilibrio de carga DNS

1. Inicie sesión en el servidor Standard Edition de Skype Empresarial Server o en un servidor front-end de Skype Empresarial Server.
    
2. Una vez allí, abra el Generador de **topologías de Skype Empresarial Server.**
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con el botón **secundario en Grupos de servidores perimetrales** y, a continuación, haga clic en Nuevo grupo de servidores **perimetrales.**
    
5. Haga clic en **Siguiente en** la pantalla Definir nuevo grupo de **servidores perimetrales.**
    
6. En la pantalla Definir el **FQDN** del grupo de servidores perimetrales, escriba el nombre de dominio completo  (FQDN) interno que va a usar el grupo de servidores perimetrales y seleccione Grupo de varios equipos haciendo clic en Siguiente cuando haya terminado.
    
7. En la **pantalla Seleccionar** características, puede elegir:
    
    - Es posible que tenga la intención de usar el mismo FQDN y dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Skype Empresarial Server y el servicio perimetral A/V. Si es así, debe seleccionar la casilla Usar un **solo FQDN** y dirección IP (y tenga esto en cuenta para el paso 9 a continuación)
    
    - Si tiene previsto habilitar la federación, seleccione la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061).**
    
8. Una vez que haya hecho clic en **Siguiente,** se encontrará en la pantalla **Opciones de IP.** Las opciones son las siguientes:
    
    - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estas son bastante fáciles de explicar, tanto si usa direcciones IPv4 o IPv6 como si las está aplicando en el servidor perimetral interna o externamente (tendrá que tener esto en cuenta en el paso 11). También tiene la opción de configurar el servidor perimetral o el grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red (NAT) para la dirección IP externa. Para ello, seleccione la dirección IP externa de este grupo de servidores perimetrales mediante la casilla **NAT.** Haga **clic en Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección realizada en el paso 7 anterior.
    
   - Si ha activado la casilla **Usar un solo FQDN** y una dirección IP, debe escribir el FQDN externo único en el cuadro acceso **SIP.** A continuación, tendrá que escribir números de puerto diferentes para cada servicio perimetral para permitir que todos se conecten de forma independiente. Se recomienda 5061 para el servicio perimetral de acceso **SIP,** 444 para el servicio perimetral de conferencia **web** y 443 para el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
   - Si no ha marcado la casilla Usar un **solo FQDN** y dirección IP, ahora tendrá que escribir los tres FQDN externos para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
10. Ahora has llegado a Definir los **equipos en la pantalla de este** grupo de servidores. Haga clic en el botón **Agregar**.
    
11. Ahora está en la pantalla Definir **la dirección IP** interna. Aquí escribirá la dirección IP del servidor perimetral en los cuadros de texto Dirección **IPv4** interna e **IPv6** interna, en función de las elecciones que realizó en el paso 8. Haga **clic en Siguiente** cuando esté listo.
    
12. En la **pantalla Definir la dirección IP externa,** tiene algunas opciones en función de las opciones anteriores:
    
    - Puede que esté usando un solo FQDN para todos los servicios. Si es así, escriba su dirección IPv4 o IPv6 externa (lo que use) en el cuadro de texto **Acceso SIP** y, a continuación, haga clic en **Siguiente**.
    
    - Puede que haya elegido usar tres FQDN y direcciones IP independientes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V** y, a continuación, haga clic en **Siguiente.**
    
    > [!NOTE]
    > Si no ha elegido previamente habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Eso es normal, solo tienes que ir al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer ahora en el cuadro de diálogo Definir **los equipos de este** grupo de servidores.
    
14. Mientras se  encuentra en la pantalla Definir  los equipos de este grupo de servidores, haga clic en el botón Agregar de nuevo y repita los pasos del 11 al 13 hasta que haya agregado todos los servidores perimetrales que desea tener en este grupo de servidores. Cuando finalice, haga clic en **Siguiente**.
    
15. Si decidió volver a usar NAT en el paso 8, ahora verá una pantalla con un cuadro de texto **de dirección IP** pública. Deberá escribir la dirección IPv4 o IPv6 pública que haya establecido para el servicio perimetral A/V, para que NAT la traduzca. A continuación, haga clic en **Siguiente**.
    
16. La siguiente pantalla es **Definir el próximo salto.** En el **cuadro Grupo de servidores del** próximo salto, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. A continuación, haga clic en **Siguiente**.
    
17. En la **pantalla** Asociar grupos de servidores front-end, deberá especificar uno o más grupos de servidores internos, incluidos los grupos de servidores front-end y los grupos de servidores Standard Edition, para asociarlo a este servidor perimetral. Solo tiene que elegir los nombres de los grupos de servidores internos que desee usar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo que se debe tener en cuenta aquí es que, si los grupos de servidores internos o los servidores independientes ya usan un servidor perimetral de Skype Empresarial Server diferente, no pueden tener varias asociaciones. Si elige un grupo de servidores interno o un servidor independiente que se encuentra en esa situación, verá una advertencia que le indica sobre el otro servidor perimetral y puede decidir si desea continuar o no. Si continúa con esta nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
18. Haga **clic en Finalizar** en la siguiente pantalla.
    
19. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de Implementar servidores perimetrales en Skype Empresarial [Server](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definición de la topología para un grupo de servidores perimetrales con equilibrio de carga de hardware

1. Inicie sesión en el servidor Standard Edition de Skype Empresarial Server o en un servidor front-end de Skype Empresarial Server.
    
2. Una vez allí, abra el Generador de **topologías de Skype Empresarial Server.**
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con el botón **secundario en Grupos de servidores perimetrales** y, a continuación, haga clic en Nuevo grupo de servidores **perimetrales.**
    
5. Haga clic en **Siguiente en** la pantalla Definir nuevo grupo de **servidores perimetrales.**
    
6. En la pantalla Definir el **FQDN** del grupo de servidores perimetrales, escriba el nombre de dominio completo  (FQDN) interno que va a usar el grupo de servidores perimetrales y seleccione Grupo de varios equipos haciendo clic en Siguiente cuando haya terminado.
    
7. En la **pantalla Seleccionar** características, puede elegir:
    
   - Es posible que tenga la intención de usar el mismo FQDN y dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Skype Empresarial Server y el servicio perimetral A/V. Si es así, debe seleccionar la casilla Usar un **solo FQDN** y dirección IP (y tenga esto en cuenta para el paso 9 a continuación)
    
   - Si tiene previsto habilitar la federación, seleccione la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061).**
    
8. Una vez que haya hecho clic en **Siguiente,** se encontrará en la pantalla **Opciones de IP.** Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estas son bastante fáciles de explicar, tanto si usa direcciones IPv4 o IPv6 como si las está aplicando en el servidor perimetral interna o externamente (tendrá que tener esto en cuenta en el paso 11).
    
     > [!NOTE]
     > A diferencia de las otras dos opciones de  topología, al usar un equilibrador de carga de hardware, NO DEBE seleccionar la opción La dirección IP externa del grupo de servidores perimetrales se traduce **mediante NAT.** Esto no **es compatible.**
  
9. En la pantalla FQDN externos, las opciones dependen de la selección realizada en el paso 7 anterior.
    
   - Si ha activado la casilla **Usar un solo FQDN** y una dirección IP, debe escribir el FQDN externo único en el cuadro acceso **SIP.** A continuación, tendrá que escribir números de puerto diferentes para cada servicio perimetral para permitir que todos se conecten de forma independiente. Se recomienda 5061 para el servicio perimetral de acceso **SIP,** 444 para el servicio perimetral de conferencia **web** y 443 para el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
   - Si no ha marcado la casilla Usar un **solo FQDN** y dirección IP, ahora tendrá que escribir los tres FQDN externos para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
10. Ahora has llegado a Definir los **equipos en la pantalla de este** grupo de servidores. Haga clic en el botón **Agregar**.
    
11. Ahora está en la pantalla Definir **la dirección IP** interna. Aquí escribirá la dirección IP del servidor perimetral en los cuadros de texto Dirección **IPv4** interna e **IPv6** interna, en función de las elecciones que realizó en el paso 8. Haga **clic en Siguiente** cuando esté listo.
    
12. En la **pantalla Definir la dirección IP externa,** tiene algunas opciones en función de las opciones anteriores:
    
    - Puede que esté usando un solo FQDN para todos los servicios. Si es así, escriba su dirección IPv4 o IPv6 externa (lo que use) en el cuadro de texto **Acceso SIP** y, a continuación, haga clic en **Siguiente**.
    
    - Puede que haya elegido usar tres FQDN y direcciones IP independientes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V** y, a continuación, haga clic en **Siguiente.**
    
    > [!NOTE]
    > Si no ha elegido previamente habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Eso es normal, solo tienes que ir al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer ahora en el cuadro de diálogo Definir **los equipos de este** grupo de servidores.
    
14. Mientras se  encuentra en la pantalla Definir  los equipos de este grupo de servidores, haga clic en el botón Agregar de nuevo y repita los pasos del 11 al 13 hasta que haya agregado todos los servidores perimetrales que desea tener en este grupo de servidores. Cuando finalice, haga clic en **Siguiente**.
    
15. La siguiente pantalla es **Definir el próximo salto.** En el **cuadro Grupo de servidores del** próximo salto, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. A continuación, haga clic en **Siguiente**.
    
16. En la **pantalla** Asociar grupos de servidores front-end, deberá especificar uno o más grupos de servidores internos, incluidos los grupos de servidores front-end y los grupos de servidores Standard Edition, para asociarlo a este servidor perimetral. Solo tiene que elegir los nombres de los grupos de servidores internos que desee usar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo que se debe tener en cuenta aquí es que, si los grupos de servidores internos o los servidores independientes ya usan un servidor perimetral de Skype Empresarial Server diferente, no pueden tener varias asociaciones. Si elige un grupo de servidores interno o un servidor independiente que se encuentra en esa situación, verá una advertencia que le indica sobre el otro servidor perimetral y puede decidir si desea continuar o no. Si continúa con esta nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
17. Haga **clic en Finalizar** en la siguiente pantalla.
    
18. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de Implementar servidores perimetrales en Skype Empresarial [Server](deploy-edge-servers.md) para implementar en el servidor perimetral desde aquí.
    
## <a name="publish-your-edge-server-topology"></a>Publicar la topología del servidor perimetral

Una vez que haya terminado los pasos anteriores, es el momento de publicar esta nueva topología, que también le permitirá exportarla a su servidor perimetral o grupo de servidores perimetrales de Skype Empresarial Server. Siga estos pasos:
  
1. Inicie **topology Builder** (si aún no se ha iniciado desde el procedimiento anterior).
    
2. En **el Generador de topologías,** en el árbol de consola, haga clic con el botón secundario en Skype Empresarial **Server** y, a continuación, haga clic en Generador de topologías de Skype Empresarial **Server.**
    
3. En la página **principal** del Asistente, haga clic en **Siguiente**.
    
4. En la página **Crear otras bases de datos**, haga clic en **Siguiente**.
    
5. Cuando el estado indique que la creación de la base de datos se ha creado correctamente, haga lo siguiente:
    
    - Para visualizar el registro, haga clic en **Ver registro**.
    
    - Para cerrar el asistente, haga clic en **Finalizar**.
    
## <a name="export-your-edge-server-topology"></a>Exportar la topología del servidor perimetral

Para implementar correctamente, el Asistente para la implementación de Skype Empresarial Server necesita acceso a los datos del almacén de administración central. En el caso de los servidores internos de su dominio o bosque, esto suele ser sencillo. Los servidores perimetrales están fuera del dominio, por lo que es necesario exportar manualmente el archivo de topología a la ubicación del servidor perimetral, normalmente en un medio físico. Esta exportación se realiza a través de PowerShell:
  
1. Inicie el **Shell de administración de Skype Empresarial Server.**
    
2. En el **Shell de administración de Skype Empresarial Server,** ejecute lo siguiente:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copia el archivo exportado a medios externos (por ejemplo, una unidad USB o un recurso compartido de red al que puedas acceder desde la ubicación del servidor perimetral).
    

