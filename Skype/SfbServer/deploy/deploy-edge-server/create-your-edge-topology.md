---
title: Crear la topología perimetral para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumen: obtenga información sobre cómo crear, publicar y exportar la topología del servidor perimetral en Skype Empresarial Server.'
ms.openlocfilehash: b016475f32e38b1353f7ef14f91e203843cd748b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844863"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Crear la topología perimetral para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear, publicar y exportar la topología del servidor perimetral en Skype Empresarial Server.
  
Topology Builder es la herramienta que necesita usar para crear la topología del servidor perimetral, tal como se usa para cualquier componente de topología para Skype Empresarial Server. Antes de seguir los pasos siguientes, deberá haber configurado al menos un grupo de servidores front-end o un Standard Edition servidor.
  
Tratamos los siguientes temas de este artículo:
  
- Crear la topología del servidor perimetral
    
- Publicar la topología del servidor perimetral
    
- Exportar la topología del servidor perimetral
    
  > [!NOTE]
  > Para seguir los pasos siguientes, tendrá que iniciar sesión en los servidores de dominio mencionados a continuación como un usuario que sea miembro de los siguientes grupos de dominios: 
  
- RTCUniversalServerAdmins
    
- Administradores de dominio
    
## <a name="build-your-edge-server-topology"></a>Crear la topología del servidor perimetral

El primer paso de implementación es crear la topología Skype Empresarial Server servidor perimetral, que consta de una de tres opciones:
  
- Un único servidor perimetral
    
- Un grupo de servidores perimetrales con equilibrio de carga DNS (uno o más servidores)
    
- Un grupo perimetral equilibrado de carga de hardware (uno o más servidores)
    
Si no está seguro de lo que necesita, antes de empezar a seguir estos pasos, es un buen momento para rebaúr la documentación de planeación. De lo contrario, empecemos.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definición de la topología de un solo servidor perimetral

1. Inicie sesión en el Skype Empresarial Server Standard Edition o en un grupo Skype Empresarial Server front-end.
    
2. Una vez allí, **abra Skype Empresarial Server Generador de topologías**.
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con el botón secundario en **Grupos perimetrales** y, a continuación, haga clic **en Nuevo grupo de servidores perimetrales.**
    
5. Haga clic en **Siguiente en** la pantalla Definir nuevo grupo **de servidores** perimetrales.
    
6. En la pantalla Definir **el FQDN** del grupo de servidores perimetrales, escriba el nombre de dominio completo  (FQDN) interno que va a usar el servidor perimetral y seleccione Grupo de servidores de un solo **equipo,** haciendo clic en Siguiente cuando haya terminado.
    
7. En la **pantalla Seleccionar características,** tienes una opción:
    
   - Es posible que tenga la intención de usar el mismo FQDN y dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Skype Empresarial Server y el servicio perimetral A/V. Si es así, debe elegir la casilla Usar un **solo FQDN** y dirección IP (y tenga esto en cuenta para el paso 9 siguiente)
    
   - Si planea habilitar la federación, seleccione la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061).**
    
8. Una vez que hayas hecho clic en **Siguiente,** te encontrarás en la pantalla **Opciones de IP.** Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
   Estas son bastante explicativas, ya sea que estés usando direcciones IPv4 o IPv6 y estés aplicando esas direcciones en el servidor perimetral de forma interna o externa (tendrás que tener esto en cuenta para el paso 10). También tiene la opción de configurar el servidor perimetral o el grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red (NAT) para la dirección IP externa. Para ello, seleccione la casilla de verificación La dirección IP externa de este grupo de servidores perimetrales se traduce mediante **NAT.** Haga **clic en Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección realizada en el paso 7 anterior.
    
   - Si ha activado la casilla Usar un **solo FQDN** y dirección IP, debe escribir el FQDN externo único en el cuadro **Acceso SIP.** A continuación, deberá escribir números de puerto diferentes para cada servicio perimetral para permitir que todos se conecten de forma independiente. Se recomienda 5061 para el servicio perimetral de acceso **SIP,** 444 para el servicio perimetral de conferencia **web** y 443 para el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
   - Si no ha marcado la casilla Usar un solo FQDN y dirección **IP,** ahora deberá escribir los tres FQDN externos para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
10. Ahora está en la pantalla **Definir la dirección IP** interna. Aquí escribirá la dirección IP del servidor perimetral en los cuadros de texto Dirección **IPv4** interna y Dirección **IPv6** interna, en función de las opciones que ha tomado en el paso 8. Haga **clic en Siguiente** cuando esté listo.
    
11. En la **pantalla Definir la dirección IP externa,** tiene algunas opciones según las opciones anteriores:
    
    - Puede que esté usando un solo FQDN para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (independientemente de lo que use) en el cuadro de texto **Acceso SIP** y, a continuación, haga clic en **Siguiente**.
    
    - Es posible que haya elegido usar tres FQDN y direcciones IP independientes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V** y, a continuación, haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si no ha elegido anteriormente habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Eso es normal, simplemente vaya al paso siguiente. 
  
12. Si optó por volver a usar NAT en el paso 8, ahora tendrá una pantalla con un cuadro de texto **dirección IP** pública. Deberá escribir la dirección IPv4 o IPv6 pública que haya establecido para el servicio perimetral A/V, que NAT traducirá. A continuación, haga clic en **Siguiente**.
    
13. La siguiente pantalla hacia arriba **es Definir el próximo salto**. En el **cuadro Grupo de servidores de próximo** salto, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. A continuación, haga clic en **Siguiente**.
    
14. En la **pantalla** Asociar grupos de servidores front-end, deberá especificar uno o varios grupos de servidores internos, incluidos los grupos de servidores front-end y los servidores Standard Edition, para asociarlo con este servidor perimetral. Simplemente elija los nombres de los grupos de servidores internos que desea usar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo que hay que tener en cuenta aquí es que, si los grupos de servidores internos o los servidores independientes ya usan un servidor perimetral Skype Empresarial Server, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, verá una advertencia que le avisará sobre el otro servidor perimetral y podrá decidir si desea continuar o no. Si continúa con esta nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
15. Haga **clic en** Finalizar en la siguiente pantalla.
    
16. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de Implementar servidores perimetrales en [Skype Empresarial Server](deploy-edge-servers.md) implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definición de la topología de un grupo de servidores perimetrales con equilibrio de carga DNS

1. Inicie sesión en el Skype Empresarial Server Standard Edition o en un Skype Empresarial Server front-end.
    
2. Una vez allí, **abra Skype Empresarial Server Generador de topologías**.
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con el botón secundario en **Grupos perimetrales** y, a continuación, haga clic **en Nuevo grupo de servidores perimetrales.**
    
5. Haga clic en **Siguiente en** la pantalla Definir nuevo grupo **de servidores** perimetrales.
    
6. En la pantalla Definir **el FQDN** del grupo de servidores perimetrales, escriba el nombre de dominio completo  (FQDN) interno que va a usar el grupo de servidores perimetrales y seleccione Grupo de servidores de varios **equipos,** haciendo clic en Siguiente cuando haya terminado.
    
7. En la **pantalla Seleccionar características,** tienes una opción:
    
    - Es posible que tenga la intención de usar el mismo FQDN y dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Skype Empresarial Server y el servicio perimetral A/V. Si es así, debe elegir la casilla Usar un **solo FQDN** y dirección IP (y tenga esto en cuenta para el paso 9 siguiente)
    
    - Si planea habilitar la federación, seleccione la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061).**
    
8. Una vez que hayas hecho clic en **Siguiente,** te encontrarás en la pantalla **Opciones de IP.** Las opciones son las siguientes:
    
    - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estas son bastante explicativas, ya sea que estés usando direcciones IPv4 o IPv6 y estés aplicando esas direcciones en el servidor perimetral de forma interna o externa (tendrás que tener esto en cuenta para el paso 11). También tiene la opción de configurar el servidor perimetral o el grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red (NAT) para la dirección IP externa. Para ello, seleccione la casilla de verificación La dirección IP externa de este grupo de servidores perimetrales se traduce mediante **NAT.** Haga **clic en Siguiente** cuando esté listo.
    
9. En la pantalla FQDN externos, las opciones dependen de la selección realizada en el paso 7 anterior.
    
   - Si ha activado la casilla Usar un **solo FQDN** y dirección IP, debe escribir el FQDN externo único en el cuadro **Acceso SIP.** A continuación, deberá escribir números de puerto diferentes para cada servicio perimetral para permitir que todos se conecten de forma independiente. Se recomienda 5061 para el servicio perimetral de acceso **SIP,** 444 para el servicio perimetral de conferencia **web** y 443 para el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
   - Si no ha marcado la casilla Usar un solo FQDN y dirección **IP,** ahora deberá escribir los tres FQDN externos para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
10. Ahora has llegado a la **pantalla Definir los equipos de este** grupo de servidores. Haga clic en el botón **Agregar**.
    
11. Ahora está en la pantalla **Definir la dirección IP** interna. Aquí escribirá la dirección IP del servidor perimetral en los cuadros de texto Dirección **IPv4** interna y Dirección **IPv6** interna, en función de las opciones que ha tomado en el paso 8. Haga **clic en Siguiente** cuando esté listo.
    
12. En la **pantalla Definir la dirección IP externa,** tiene algunas opciones según las opciones anteriores:
    
    - Puede que esté usando un solo FQDN para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (independientemente de lo que use) en el cuadro de texto **Acceso SIP** y, a continuación, haga clic en **Siguiente**.
    
    - Es posible que haya elegido usar tres FQDN y direcciones IP independientes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V** y, a continuación, haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si no ha elegido anteriormente habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Eso es normal, simplemente vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer en el cuadro de diálogo **Definir los equipos de este** grupo de servidores.
    
14. Mientras sigue  en la pantalla Definir los  equipos de este grupo de servidores, haga clic de nuevo en el botón Agregar y repita los pasos del 11 al 13 hasta que haya agregado todos los servidores perimetrales que desea tener en este grupo de servidores. Cuando se complete, haga clic en **Siguiente**.
    
15. Si optó por volver a usar NAT en el paso 8, ahora tendrá una pantalla con un cuadro de texto **dirección IP** pública. Deberá escribir la dirección IPv4 o IPv6 pública que haya establecido para el servicio perimetral A/V, que NAT traducirá. A continuación, haga clic en **Siguiente**.
    
16. La siguiente pantalla hacia arriba **es Definir el próximo salto**. En el **cuadro Grupo de servidores de próximo** salto, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. A continuación, haga clic en **Siguiente**.
    
17. En la **pantalla** Asociar grupos de servidores front-end, deberá especificar uno o varios grupos de servidores internos, incluidos los grupos de servidores front-end y los grupos de servidores Standard Edition, para asociarlo con este servidor perimetral. Simplemente elija los nombres de los grupos de servidores internos que desea usar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo que hay que tener en cuenta aquí es que, si los grupos de servidores internos o los servidores independientes ya usan un servidor perimetral Skype Empresarial Server, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, verá una advertencia que le avisará sobre el otro servidor perimetral y podrá decidir si desea continuar o no. Si continúa con esta nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
18. Haga **clic en** Finalizar en la siguiente pantalla.
    
19. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de Implementar servidores perimetrales en [Skype Empresarial Server](deploy-edge-servers.md) implementar en el servidor perimetral desde aquí.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definición de la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware

1. Inicie sesión en el Skype Empresarial Server Standard Edition o en un Skype Empresarial Server front-end.
    
2. Una vez allí, **abra Skype Empresarial Server Generador de topologías**.
    
3. En el árbol de consola, expanda el sitio en el que va a implementar el servidor perimetral.
    
4. Haga clic con el botón secundario en **Grupos perimetrales** y, a continuación, haga clic **en Nuevo grupo de servidores perimetrales.**
    
5. Haga clic en **Siguiente en** la pantalla Definir nuevo grupo **de servidores** perimetrales.
    
6. En la pantalla Definir **el FQDN** del grupo de servidores perimetrales, escriba el nombre de dominio completo  (FQDN) interno que va a usar el grupo de servidores perimetrales y seleccione Grupo de servidores de varios **equipos,** haciendo clic en Siguiente cuando haya terminado.
    
7. En la **pantalla Seleccionar características,** tienes una opción:
    
   - Es posible que tenga la intención de usar el mismo FQDN y dirección IP para el servicio de acceso SIP, el servicio de conferencia web de Skype Empresarial Server y el servicio perimetral A/V. Si es así, debe elegir la casilla Usar un **solo FQDN** y dirección IP (y tenga esto en cuenta para el paso 9 siguiente)
    
   - Si planea habilitar la federación, seleccione la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061).**
    
8. Una vez que hayas hecho clic en **Siguiente,** te encontrarás en la pantalla **Opciones de IP.** Las opciones son las siguientes:
    
   - Habilitar IPv4 en la interfaz interna
    
   - Habilitar IPv6 en la interfaz interna
    
   - Habilitar IPv4 en la interfaz externa
    
   - Habilitar IPv6 en la interfaz externa
    
     Estas son bastante explicativas, ya sea que estés usando direcciones IPv4 o IPv6 y estés aplicando esas direcciones en el servidor perimetral de forma interna o externa (tendrás que tener esto en cuenta para el paso 11).
    
     > [!NOTE]
     > A diferencia de las otras dos opciones de  topología, al usar un equilibrador de carga de hardware, NO debe seleccionar la opción La dirección IP externa del grupo de servidores perimetrales se traduce mediante **NAT**. No se **admite**.
  
9. En la pantalla FQDN externos, las opciones dependen de la selección realizada en el paso 7 anterior.
    
   - Si ha activado la casilla Usar un **solo FQDN** y dirección IP, debe escribir el FQDN externo único en el cuadro **Acceso SIP.** A continuación, deberá escribir números de puerto diferentes para cada servicio perimetral para permitir que todos se conecten de forma independiente. Se recomienda 5061 para el servicio perimetral de acceso **SIP,** 444 para el servicio perimetral de conferencia **web** y 443 para el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
   - Si no ha marcado la casilla Usar un solo FQDN y dirección **IP,** ahora deberá escribir los tres FQDN externos para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V.** Seleccione **Siguiente** cuando termine.
    
10. Ahora has llegado a la **pantalla Definir los equipos de este** grupo de servidores. Haga clic en el botón **Agregar**.
    
11. Ahora está en la pantalla **Definir la dirección IP** interna. Aquí escribirá la dirección IP del servidor perimetral en los cuadros de texto Dirección **IPv4** interna y Dirección **IPv6** interna, en función de las opciones que ha tomado en el paso 8. Haga **clic en Siguiente** cuando esté listo.
    
12. En la **pantalla Definir la dirección IP externa,** tiene algunas opciones según las opciones anteriores:
    
    - Puede que esté usando un solo FQDN para todos los servicios. Si es así, escriba la dirección IPv4 o IPv6 externa (independientemente de lo que use) en el cuadro de texto **Acceso SIP** y, a continuación, haga clic en **Siguiente**.
    
    - Es posible que haya elegido usar tres FQDN y direcciones IP independientes para los servicios. Si ese es el caso, escriba las direcciones IPv4 o IPv6 externas para el servicio perimetral de acceso **SIP,** el servicio perimetral de conferencia **web** y el servicio perimetral **A/V** y, a continuación, haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si no ha elegido anteriormente habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo. Eso es normal, simplemente vaya al paso siguiente. 
  
13. Haga clic en **Finalizar**. El servidor perimetral que acaba de crear debería aparecer en el cuadro de diálogo **Definir los equipos de este** grupo de servidores.
    
14. Mientras sigue  en la pantalla Definir los  equipos de este grupo de servidores, haga clic de nuevo en el botón Agregar y repita los pasos del 11 al 13 hasta que haya agregado todos los servidores perimetrales que desea tener en este grupo de servidores. Cuando se complete, haga clic en **Siguiente**.
    
15. La siguiente pantalla hacia arriba **es Definir el próximo salto**. En el **cuadro Grupo de servidores de próximo** salto, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo independiente. Si tiene un director en su entorno, debe elegir el director. A continuación, haga clic en **Siguiente**.
    
16. En la **pantalla** Asociar grupos de servidores front-end, deberá especificar uno o varios grupos de servidores internos, incluidos los grupos de servidores front-end y los grupos de servidores Standard Edition, para asociarlo con este servidor perimetral. Simplemente elija los nombres de los grupos de servidores internos que desea usar este servidor perimetral para comunicarse con usuarios externos compatibles. Haga clic en **Siguiente**.
    
    > [!NOTE]
    > Algo que hay que tener en cuenta aquí es que, si los grupos de servidores internos o los servidores independientes ya usan un servidor perimetral Skype Empresarial Server, no pueden tener varias asociaciones. Si elige un grupo interno o un servidor independiente que se encuentra en esa situación, verá una advertencia que le avisará sobre el otro servidor perimetral y podrá decidir si desea continuar o no. Si continúa con esta nueva asociación, se detendrá la conexión con el otro servidor perimetral. 
  
17. Haga **clic en** Finalizar en la siguiente pantalla.
    
18. Ahora podrá publicar esta tecnología actualizada y seguir las instrucciones de Implementar servidores perimetrales en [Skype Empresarial Server](deploy-edge-servers.md) implementar en el servidor perimetral desde aquí.
    
## <a name="publish-your-edge-server-topology"></a>Publicar la topología del servidor perimetral

Una vez que haya terminado los pasos anteriores, es el momento de publicar esta nueva topología, que también le permitirá exportarla al servidor perimetral de Skype Empresarial Server o grupo de servidores perimetrales. Siga estos pasos:
  
1. Inicie **el Generador de** topologías (si aún no se ha iniciado desde el procedimiento anterior).
    
2. En **el Generador de topologías**, en el árbol de consola, haga clic con el botón secundario en **Skype Empresarial Server** y, a continuación, haga clic Skype Empresarial Server Generador **de topologías**.
    
3. En la página **principal** del Asistente, haga clic en **Siguiente**.
    
4. En la página **Crear otras bases de datos**, haga clic en **Siguiente**.
    
5. Cuando el estado indique que la creación de la base de datos se ha creado correctamente, haga lo siguiente:
    
    - Para visualizar el registro, haga clic en **Ver registro**.
    
    - Para cerrar el asistente, haga clic en **Finalizar**.
    
## <a name="export-your-edge-server-topology"></a>Exportar la topología del servidor perimetral

Para implementarse correctamente, el Asistente Skype Empresarial Server de implementación necesita acceso a los datos del almacén de administración central. En el caso de los servidores internos de su dominio o bosque, esto suele ser sencillo. Los servidores perimetrales están fuera del dominio, por lo que es necesario exportar manualmente el archivo de topología a la ubicación del servidor perimetral, normalmente en un medio físico. Esta exportación se realiza a través de PowerShell:
  
1. Inicie el **Shell Skype Empresarial Server administración**.
    
2. En el **Shell Skype Empresarial Server administración**, ejecute lo siguiente:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie el archivo exportado a medios externos (por ejemplo, una unidad USB o un recurso compartido de red al que pueda llegar desde la ubicación del servidor perimetral).
    

