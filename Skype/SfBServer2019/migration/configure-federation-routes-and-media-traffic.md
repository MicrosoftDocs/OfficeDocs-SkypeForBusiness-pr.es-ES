---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de red. Después de migrar a su grupo piloto, necesitará para la transición desde la ruta de federación de las versiones anteriores de los servidores perimetrales para la ruta de federación de su Skype para los servidores perimetrales de Business Server 2019.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880231"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de red. Después de migrar a su grupo piloto, necesitará para la transición desde la ruta de federación de los servidores perimetrales de la versión anterior a la ruta de federación de su Skype para los servidores perimetrales de Business Server 2019.
  
Use los siguientes procedimientos para realizar la transición de la ruta de federación y la ruta de tráfico de medios de servidor perimetral y Director de la versión anterior a su Skype para servidor perimetral de Business Server 2019, para una implementación de sitio único.
  
> [!IMPORTANT]
> Cambiar la ruta de federación y la ruta de tráfico multimedia requiere programar el tiempo de inactividad de mantenimiento para la Skype para Business Server 2019 y los servidores perimetrales de versión anterior. Este proceso de transición completa también significa que acceso federado dejarán de estar disponible para la duración de la interrupción del servicio. Debe programar el tiempo de inactividad durante un tiempo cuando se espera actividad mínima del usuario. También debe proporcionar suficiente notificación a los usuarios finales. Planear en consecuencia para esta interrupción y el conjunto adecuado las expectativas dentro de la organización. 
  
> [!IMPORTANT]
> Si su servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio de servidor perimetral de acceso, servicio perimetral de conferencia Web y el servicio perimetral A/v, los procedimientos descritos en esta sección no son compatibles. Si los Servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios luego dé de baja el servidor perimetral de versiones anteriores antes de habilitar la federación en el Skype para servidor perimetral de Business Server 2019. 
  
> [!IMPORTANT]
> Si la federación XMPP se enruta a través de un Skype para servidor perimetral de Business Server 2019, los usuarios en la versión anterior no podrán comunicarse con el socio federado XMPP hasta que todos los usuarios se han movido a Skype para Business Server 2019, directivas de XMPP y se han configurado los certificados, se ha configurado el socio federado XMPP en Skype para Business Server 2019 y, por último, se han actualizado las entradas DNS. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para quitar la asociación de federación heredada de Skype para sitios de Business Server 2019

1. En Skype para servidor Front-End de Business Server 2019, abra la topología existente en el generador de topología. 
    
2. En el panel izquierdo, desplácese hasta el nodo del sitio, que se encuentra justo debajo de **Skype para Business Server**.
    
3. Haga clic en el sitio y, a continuación, haga clic en **Editar propiedades**.
    
4. En el panel izquierdo, seleccione **ruta de federación**. 
    
5. En **asignación de ruta de federación de sitio**, desactive la casilla de verificación **Habilitar federación SIP** para deshabilitar la ruta de federación a través del entorno heredado. 
  
6. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
7. En **El generador de topología**, seleccione el nodo superior **Skype para Business Server**.
    
8. En el menú **acción** , haga clic en **Publicar topología**.
    
9. Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando haya finalizado el proceso de publicación. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral heredado como un servidor perimetral no federado

1. En el panel izquierdo, desplácese al nodo instalar heredado y, a continuación, en el nodo de **perimetral grupos de servidores** . 
    
2. Haga clic en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel izquierdo. 
    
4. Desactive la casilla de verificación **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página. 
  
5. En el menú **acción** , seleccione **Publicar topología**y, a continuación, haga clic en **siguiente**.
    
6. Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar** para cerrar al asistente. 
    
7. Compruebe que está deshabilitada la federación para el servidor perimetral heredado en el generador de topología.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados en el servidor perimetral heredado

1. Exporte el certificado externo del Proxy de acceso, con la clave privada, desde el servidor perimetral heredado. 
    
2. En el Skype para servidor perimetral de Business Server 2019 e importar el Proxy de acceso externo de certificados desde el paso anterior.
    
3. Asignar el certificado externo del Proxy de acceso a la Skype para Business Server 2019 la interfaz externa del servidor perimetral.
    
4. El certificado de la interfaz interna de la Skype para servidor perimetral de Business Server 2019 debe solicitar a una CA de confianza y asignarse. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para cambiar la ruta de federación de la versión anterior para usar Skype para servidor perimetral de Business Server 2019

1. En Topology Builder, en el panel izquierdo, desplácese al nodo de **Skype para Business Server 2019** y, a continuación, en el nodo de **grupos de servidores perimetrales** . 
    
2. Haga clic en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel izquierdo. 
    
4. Seleccione la casilla de verificación para **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página. 
  
5. En el menú **acción** , seleccione **Publicar topología**y, a continuación, haga clic en **siguiente**.
    
6. Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar** para cerrar al asistente. 
    
7. Compruebe que **federación (puerto 5061)** se establece en **habilitado** en el generador de topología.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para actualizar Skype para el próximo salto de federación de servidor perimetral de Business Server 2019

1. En Topology Builder, en el panel izquierdo, desplácese al nodo de **Skype para Business Server 2019** y, a continuación, en el nodo de **grupos de servidores perimetrales** . 
    
2. Expanda el nodo, haga clic en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**. 
    
3. En la página **General** , en **selección de próximo salto**, seleccione en la lista desplegable el Skype para el grupo de servidores de Business Server 2019.
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. En **El generador de topología**, seleccione el nodo superior **Skype para Business Server**. 
    
6. En el menú **acción** , haga clic en **Publicar topología** y complete el asistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar Skype para la ruta de acceso de servidor perimetral de Business Server 2019 medios de salida

1. En Topology Builder, en el panel izquierdo, desplácese al nodo **Skype para Business Server 2019** y, a continuación, en el grupo de servidores por debajo de **Standard Edition servidor front-end** o **grupos de servidores Front-End de Enterprise Edition**.
    
2. Haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.
    
3. En la sección **asociaciones** , active la casilla de verificación de **grupo de servidores perimetrales asociados (para componentes multimedia)** . 
  
4. En el cuadro de lista desplegable, seleccione el Skype para servidor perimetral de Business Server 2019.
    
5. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para activar Skype para la federación del servidor perimetral de Business Server 2019

1. En Topology Builder, en el panel izquierdo, desplácese al nodo de **Skype para Business Server 2019** y, a continuación, en el nodo de **grupos de servidores perimetrales** . 
    
2. Expanda el nodo, haga clic en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**. 
    
    > [!NOTE]
    > Sólo se puede habilitar la federación para un único grupo de servidores perimetrales. Si tiene varios grupos de servidores perimetrales, seleccione una nueva para usarla como el grupo de servidores perimetrales federación. 
  
3. En la página **General** , compruebe que está activada la casilla de verificación **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** . 
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. Vaya al nodo del sitio. 
    
6. Haga clic en el sitio y, a continuación, haga clic en **Editar propiedades**.
    
7. En el panel izquierdo, haga clic en **ruta de federación**.
    
8. En **asignación de ruta de federación de sitio**, seleccione **Habilitar federación SIP**y, a continuación, en la lista Seleccione la Skype para Business Server 2019 perimetral Server enumerados. 
  
9. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
     Para las implementaciones de varios sitios, complete este procedimiento en cada sitio. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar los cambios de configuración del servidor perimetral

1. En **El generador de topología**, seleccione el nodo superior **Skype para Business Server**. 
    
2. En el menú **acción** , seleccione **Publicar topología** y complete el asistente. 
    
3. Espere a que la replicación de Active Directory que se produzca a todos los grupos de servidores en la implementación.
    
    > [!NOTE]
    > Es posible que aparezca el siguiente mensaje: **Advertencia: la topología contiene más de un servidor perimetral federados. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, un solo servidor perimetral se usaría activamente para la federación. Compruebe que el registro SRV de DNS externo señala al servidor perimetral correcto. Si desea implementar varios federación servidor perimetral para ser al mismo tiempo activo (es decir, no un escenario de migración), compruebe que todos los socios federados usa Skype para Business Server. Compruebe que el registro SRV de DNS externo enumera todos los servidores perimetrales de federación habilitada.** Se espera y se puede omitir esta advertencia. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar Skype para servidor perimetral de Business Server 2019

1. Conecte todos los de la Skype para los servidores perimetrales de Business Server 2019 en línea. 
    
2. Actualizar las reglas de enrutamiento de firewall externo o la configuración de equilibrador de carga de hardware para enviar el tráfico SIP para el acceso externo (normalmente el puerto 443) y federación (normalmente el puerto 5061) a la Skype para Business Server 2019 perimetral Server, en lugar del servidor perimetral heredado.
    
    > [!NOTE]
    > Si no es necesario un equilibrador de carga de hardware, debe actualizar el registro A DNS para la federación resolver en el nuevo Skype para servidor perimetral de acceso de servidor empresarial. Para hacerlo con una interrupción mínima, reducir el valor TLL para el Skype externo de Business Server acceso perimetral FQDN para que cuando se actualiza DNS para que apunte a la nueva Skype para el servidor perimetral de acceso de servidor empresarial, la federación y el acceso remoto se actualizarán rápidamente. 
  
3. Detener la **Skype para el servidor perimetral de acceso de servidor empresarial** desde cada equipo servidor perimetral. 
    
4. En cada equipo servidor perimetral heredado, abra el subprograma **Servicios** desde las **Herramientas administrativas**.
    
5. En la lista de servicios, busque **Skype para el servidor perimetral de acceso de servidor empresarial**.
    
6. Haga clic en el nombre de los servicios y, a continuación, seleccione **Detener** para detener el servicio. 
    
7. Establezca el tipo de inicio en **deshabilitado**. 
    
8. Haga clic en **Aceptar** para cerrar la ventana **Propiedades** . 
    

