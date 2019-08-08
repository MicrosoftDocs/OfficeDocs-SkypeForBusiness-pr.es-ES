---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red. Después de migrar a su grupo piloto, debe realizar una transición de la ruta de Federación de sus servidores perimetrales de versiones anteriores a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239365"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

La Federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de la red. Después de migrar a su grupo piloto, debe realizar una transición de la ruta de Federación de los servidores perimetrales de la versión anterior a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.
  
Use los procedimientos siguientes para realizar la transición de la ruta de Federación y la ruta de tráfico multimedia desde el servidor perimetral y el director de la versión anterior de Skype 2019 empresarial para una implementación de sitio único.
  
> [!IMPORTANT]
> El cambio de la ruta de Federación y el tráfico de multimedia requiere que programe el tiempo de inactividad de mantenimiento de los servidores de Skype empresarial Server 2019 y versiones anteriores. Todo este proceso de transición también significa que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para una hora en la que espera una actividad mínima de usuario. También debe proporcionar una notificación suficiente a los usuarios finales. Planee en consecuencia para esta interrupción y establezca las expectativas apropiadas dentro de su organización. 
  
> [!IMPORTANT]
> Si el servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral a/V, no se admiten los procedimientos de esta sección. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios y luego retirar el servidor perimetral de las versiones anteriores antes de habilitar la Federación en el servidor perimetral de Skype empresarial Server 2019. 
  
> [!IMPORTANT]
> Si la Federación de XMPP se dirige a través de un servidor perimetral de Skype empresarial Server 2019, los usuarios de la versión anterior no podrán comunicarse con el socio de XMPP federado hasta que todos los usuarios hayan pasado a Skype empresarial Server 2019, directivas XMPP y se han configurado certificados, el socio de XMPP federado se ha configurado en Skype empresarial Server 2019 y, por último, se han actualizado las entradas DNS. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para quitar la Asociación de Federación heredada de sitios de Skype empresarial Server 2019

1. En el servidor front-end de Skype empresarial Server 2019, abra la topología existente en el generador de topologías. 
    
2. En el panel de la izquierda, vaya al nodo del sitio, que se encuentra directamente debajo **de Skype empresarial Server**.
    
3. Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.
    
4. En el panel de la izquierda, seleccione **ruta de Federación**. 
    
5. En **asignación de ruta de Federación de sitios**, desactive la casilla **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado. 
  
6. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
7. En el **generador**de topologías, seleccione el nodo principal de **Skype empresarial Server**.
    
8. En el menú **acción** , haga clic en **publicar topología**.
    
9. Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral heredado como servidor perimetral de no Federación

1. En el panel de la izquierda, navegue hasta el nodo instalación heredada y, a continuación, al nodo contornos de **borde** . 
    
2. Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel de la izquierda. 
    
4. Desactive la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y seleccione **Aceptar** para cerrar la página. 
  
5. En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.
    
6. Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente. 
    
7. Compruebe que la Federación del servidor perimetral heredado está deshabilitada en el generador de topología.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados en el servidor perimetral heredado

1. Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral heredado. 
    
2. En el servidor perimetral de Skype empresarial Server 2019 e importe el certificado externo del proxy de acceso del paso anterior.
    
3. Asigne el certificado externo del proxy de acceso a la interfaz externa de Skype empresarial Server 2019 del servidor perimetral.
    
4. El certificado de interfaz interno del servidor perimetral de Skype empresarial Server 2019 debe solicitarse a una entidad de certificación de confianza y asignarse. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para cambiar la ruta de Federación de la versión anterior para usar Skype empresarial Server 2019 Edge Server

1. Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, al nodo de **grupos de límites** . 
    
2. Haga clic con el botón secundario en el servidor perimetral y luego haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel de la izquierda. 
    
4. Active la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página. 
  
5. En el menú **acción** , seleccione **publicar topología**y, a continuación, haga clic en **siguiente**.
    
6. Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente. 
    
7. Compruebe que la **Federación (puerto 5061)** está **habilitada** en el generador de topología.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para actualizar el próximo salto de la Federación de Skype empresarial Server 2019 Edge Server

1. Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, al nodo de **grupos de límites** . 
    
2. Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**. 
    
3. En la página **General** , en **selección del próximo salto**, seleccione de la lista desplegable el grupo de servidores de Skype empresarial 2019.
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. En el **generador**de topologías, seleccione el nodo principal de **Skype empresarial Server**. 
    
6. En el menú **acción** , haga clic en **publicar topología** y complete el asistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar la ruta multimedia de salida de Skype empresarial Server 2019 Edge Server

1. Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, a la sección de **servidores de aplicaciones para usuario de la versión Standard Edition** o a la de las **agrupaciones front-end Enterprise Edition**.
    
2. Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.
    
3. En la sección **asociaciones** , active la casilla **asociar grupo perimetral (para componentes multimedia)** . 
  
4. En el cuadro desplegable, seleccione el servidor perimetral de Skype empresarial Server 2019.
    
5. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para activar la Federación de servidores perimetrales de Skype empresarial Server 2019

1. Desde el generador de topologías, en el panel izquierdo, vaya al nodo **de Skype empresarial Server 2019** y, a continuación, al nodo de **grupos de límites** . 
    
2. Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que aparece y, a continuación, haga clic en **Editar propiedades**. 
    
    > [!NOTE]
    > La Federación solo se puede habilitar para un único grupo de borde. Si tiene varios grupos de límites, seleccione uno para usarlo como el grupo de servidores perimetrales de Federación. 
  
3. En la página **General** , compruebe que la casilla **de verificación Habilitar la Federación para este grupo perimetral (puerto 5061)** está activada. 
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. Vaya al nodo del sitio. 
    
6. Haga clic con el botón secundario en el sitio y luego haga clic en **Editar propiedades**.
    
7. En el panel de la izquierda, haga clic en **ruta de Federación**.
    
8. En **asignación de ruta de Federación de sitios**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Skype empresarial Server 2019. 
  
9. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** . 
    
     Para implementaciones de varios sitios, complete este procedimiento en cada sitio. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios en la configuración del servidor perimetral

1. En el **generador**de topologías, seleccione el nodo principal de **Skype empresarial Server**. 
    
2. En el menú **acción** , seleccione **publicar topología** y complete el asistente. 
    
3. Espere a que se produzca la replicación de Active Directory en todos los grupos de la implementación.
    
    > [!NOTE]
    > Es posible que vea el siguiente mensaje: **ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría activamente un servidor perimetral para la Federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de forma simultánea (es decir, no un escenario de migración), compruebe que todos los socios federados usen Skype empresarial Server. Compruebe que el registro SRV de DNS externo muestra todos los servidores perimetrales habilitados para la Federación.** Esta advertencia es esperada y puede ignorarse de forma segura. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar el servidor EDGE 2019 de Skype empresarial Server

1. Conecte todos los servidores perimetrales de Skype empresarial Server 2019. 
    
2. Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar el tráfico SIP para acceso externo (generalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Skype empresarial Server 2019, en lugar del servidor perimetral heredado.
    
    > [!NOTE]
    > Si no tiene un equilibrador de carga de hardware, tendrá que actualizar el registro a de DNS para que la Federación se resuelva en el nuevo servidor perimetral de acceso de Skype empresarial Server. Para lograr esto con una interrupción mínima, reduzca el valor de TLL para el FQDN del perímetro externo de acceso de Skype empresarial Server de modo que, cuando se actualice DNS para que apunte al nuevo servidor perimetral de acceso de Skype empresarial, la Federación y el acceso remoto se actualizarán rápidamente. 
  
3. Detenga el **acceso perimetral de Skype empresarial Server** desde cada equipo servidor perimetral. 
    
4. Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.
    
5. En la lista servicios, busque la **tecnología perimetral de acceso de Skype empresarial Server**.
    
6. Haga clic con el botón secundario en el nombre de servicios y, a continuación, seleccione **detener** para detener el servicio. 
    
7. Establezca el tipo de inicio **** en deshabilitado. 
    
8. Haga clic en **Aceptar** para cerrar la ventana **propiedades** . 
    

