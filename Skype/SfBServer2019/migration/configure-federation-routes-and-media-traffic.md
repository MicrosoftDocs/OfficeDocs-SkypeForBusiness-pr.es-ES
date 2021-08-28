---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto, debe pasar de la ruta de federación de sus versiones anteriores Servidores perimetrales a la ruta de federación de los servidores perimetrales de Skype Empresarial Server 2019.
ms.openlocfilehash: f051321667e12a468df1186147f6fab1d7bbe5cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613409"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto, debe pasar de la ruta de federación de los servidores perimetrales de la versión anterior a la ruta de federación de los servidores perimetrales de Skype Empresarial Server 2019.
  
Use los siguientes procedimientos para realizar la transición de la ruta de federación y la ruta de tráfico multimedia desde el servidor perimetral y el director de la versión anterior al servidor perimetral de Skype Empresarial Server 2019, para una implementación de un solo sitio.
  
> [!IMPORTANT]
> Para cambiar la ruta de federación y la ruta de tráfico multimedia, es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Skype Empresarial Server 2019 y la versión anterior. Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios. También debe notificar esta acción a los usuarios finales con antelación suficiente. Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización. 
  
> [!IMPORTANT]
> Si el servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios y, a continuación, retirar las versiones anteriores del servidor perimetral antes de habilitar la federación en el servidor perimetral de Skype Empresarial Server 2019. 
  
> [!IMPORTANT]
> Si la federación XMPP se enruta a través de un servidor perimetral de Skype Empresarial Server 2019, los usuarios de la versión anterior no podrán comunicarse con el socio federado XMPP hasta que todos los usuarios se hayan movido Skype Empresarial Server Skype Empresarial Server 2019, se hayan configurado directivas y certificados XMPP, se haya configurado el partner federado XMPP en Skype Empresarial Server 2019 y, por último, se hayan actualizado las entradas DNS. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para quitar la asociación de federación heredada de Skype Empresarial Server de 2019

1. En el Skype Empresarial Server front-end de 2019, abra la topología existente en el Generador de topologías. 
    
2. En el panel izquierdo, vaya al nodo de sitio, que se encuentra directamente debajo **de Skype Empresarial Server**.
    
3. Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.
    
4. En el panel izquierdo, seleccione **Ruta de federación**. 
    
5. En **Asignación de ruta de federación de** sitio, desactive la casilla Habilitar federación **SIP** para deshabilitar la ruta de federación a través del entorno heredado. 
  
6. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
7. En **generador de topologías,** seleccione el **nodo** superior Skype Empresarial Server .
    
8. En el menú **Acción**, haga clic en **Publicar topología**.
    
9. Haga **clic en** Siguiente para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral como servidor perimetral no federado

1. En el panel izquierdo, vaya al nodo de instalación heredado y, a continuación, al **nodo Grupos de servidores** perimetrales. 
    
2. Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel izquierdo. 
    
4. Desactive la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** y seleccione **Aceptar** para cerrar la página. 
  
5. En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.
    
6. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente. 
    
7. Compruebe que la federación del servidor perimetral heredado está deshabilitada en el Generador de topologías.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados en el servidor perimetral heredado

1. Exporte el certificado proxy de acceso externo, con la clave privada, desde el servidor perimetral heredado. 
    
2. En el Skype Empresarial Server perimetral de 2019 e importe el certificado externo proxy de acceso del paso anterior.
    
3. Asigne el certificado externo proxy de acceso a la Skype Empresarial Server interfaz externa de 2019 del servidor perimetral.
    
4. El certificado de interfaz interna del servidor perimetral Skype Empresarial Server 2019 debe solicitarse a una ENTIDAD de certificación de confianza y asignarse. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para cambiar la ruta de federación de la versión anterior para usar Skype Empresarial Server servidor perimetral de 2019

1. Desde el Generador de topologías, en el panel izquierdo, vaya al nodo **Skype Empresarial Server 2019** y, a continuación, al **nodo Grupos de servidores** perimetrales. 
    
2. Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel izquierdo. 
    
4. Active la casilla habilitar la federación para este grupo de servidores perimetrales **(puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página. 
  
5. En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.
    
6. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente. 
    
7. Compruebe que **la federación (puerto 5061)** está establecida en **Habilitado** en el Generador de topologías.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para actualizar Skype Empresarial Server de federación del servidor perimetral de 2019

1. Desde el Generador de topologías, en el panel izquierdo, vaya al nodo **Skype Empresarial Server 2019** y, a continuación, al **nodo Grupos de servidores** perimetrales. 
    
2. Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**. 
    
3. En la **página General,** en **Selección** de próximo salto, seleccione en la lista desplegable el grupo Skype Empresarial Server 2019.
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. En **generador de topologías,** seleccione el **nodo** superior Skype Empresarial Server . 
    
6. En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar Skype Empresarial Server de medios salientes del servidor perimetral de 2019

1. Desde el Generador de topologías, en el panel izquierdo, vaya al nodo **Skype Empresarial Server 2019** y, a continuación, al grupo de servidores debajo de Standard Edition servidores **front-end** o Enterprise Edition grupos de servidores front-end . 
    
2. Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.
    
3. En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**. 
  
4. En el cuadro desplegable, seleccione el Skype Empresarial Server servidor perimetral de 2019.
    
5. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para activar la Skype Empresarial Server servidor perimetral de 2019

1. Desde el Generador de topologías, en el panel izquierdo, vaya al nodo **Skype Empresarial Server 2019** y, a continuación, al **nodo Grupos de servidores** perimetrales. 
    
2. Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**. 
    
    > [!NOTE]
    > La federación solo se puede habilitar para un único grupo de servidores perimetrales. Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación. 
  
3. En la **página General,** compruebe que la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** está activada. 
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. Vaya al nodo de sitio. 
    
6. Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.
    
7. En el panel izquierdo, haga clic en **Ruta de federación**.
    
8. En **Asignación de ruta de** federación de sitio, seleccione Habilitar federación **SIP** y, a continuación, en la lista, seleccione el servidor perimetral Skype Empresarial Server 2019. 
  
9. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
     Para las implementaciones en varios sitios, complete este procedimiento en cada sitio. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios de configuración en el servidor perimetral

1. En **generador de topologías,** seleccione el **nodo** superior Skype Empresarial Server . 
    
2. En el menú **Acción**, seleccione **Publicar topología** y complete el asistente. 
    
3. Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.
    
    > [!NOTE]
    > Puede que vea el siguiente mensaje: **Advertencia: La topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la federación. Compruebe que el registro SRV dns externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (es decir, no un escenario de migración), compruebe que todos los asociados federados usan Skype Empresarial Server. Compruebe que el registro SRV de DNS externo enumera todos los servidores perimetrales habilitados para federación.** Se espera que aparezca esta advertencia y se puede omitir con toda seguridad. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar Skype Empresarial Server servidor perimetral de 2019

1. Poner en línea todos Skype Empresarial Server servidores perimetrales de 2019. 
    
2. Actualice las reglas de enrutamiento de firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para el acceso externo (normalmente el puerto 443) y la federación (normalmente el puerto 5061) al servidor perimetral de Skype Empresarial Server 2019, en lugar del servidor perimetral heredado.
    
    > [!NOTE]
    > Si no tiene un equilibrador de carga de hardware, debe actualizar el registro DNS A para que la federación se resuelva en el nuevo Skype Empresarial Server servidor perimetral de acceso. Para ello con una interrupción mínima, reduzca el valor de TLL para el FQDN perimetral de acceso externo de Skype Empresarial Server de modo que cuando DNS se actualice para que apunte al nuevo servidor perimetral de acceso de Skype Empresarial Server, la federación y el acceso remoto se actualizarán rápidamente. 
  
3. Detenga el **Skype Empresarial Server de acceso de** cada equipo servidor perimetral. 
    
4. En cada equipo servidor perimetral heredado, abra el applet **Servicios** desde **herramientas administrativas**.
    
5. En la lista de servicios, **busque Skype Empresarial Server edge de acceso**.
    
6. Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio. 
    
7. Establezca el Tipo de inicio en **Deshabilitado**. 
    
8. Haga clic en **Aceptar** para cerrar la ventana **Propiedades**. 
    

