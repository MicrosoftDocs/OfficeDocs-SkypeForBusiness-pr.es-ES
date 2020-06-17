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
localization_priority: Normal
description: La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto, debe realizar la transición de la ruta de Federación de los servidores perimetrales de versiones anteriores a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754040"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar las rutas de federación y el tráfico multimedia

La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes. Después de migrar al grupo piloto, debe realizar la transición de la ruta de Federación de los servidores perimetrales de la versión anterior a la ruta de Federación de sus servidores perimetrales de Skype empresarial Server 2019.
  
Use los siguientes procedimientos para realizar la transición de la ruta de Federación y la ruta de tráfico de medios desde el servidor perimetral y el director de la versión anterior a su servidor perimetral de Skype empresarial Server 2019 para una implementación en un solo sitio.
  
> [!IMPORTANT]
> Para cambiar la ruta de Federación y la ruta de tráfico de medios es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Skype empresarial Server 2019 y versiones anteriores. Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción. Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios. También debe notificar esta acción a los usuarios finales con antelación suficiente. Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización. 
  
> [!IMPORTANT]
> Si el servidor perimetral heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos descritos en esta sección. Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios y, a continuación, retirar el servidor perimetral de las versiones anteriores antes de habilitar la Federación en el servidor perimetral de Skype empresarial Server 2019. 
  
> [!IMPORTANT]
> Si la Federación de XMPP se enruta a través de un servidor perimetral de Skype empresarial Server 2019, los usuarios de la versión anterior no podrán comunicarse con el socio federado de XMPP hasta que todos los usuarios se hayan movido a Skype empresarial Server 2019, se hayan configurado las directivas y los certificados de XMPP, el socio federado de XMPP se ha configurado en Skype empresarial Server 2019 y, por último, se han actualizado las entradas DNS. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para quitar la Asociación de Federación heredada de los sitios de Skype empresarial Server 2019

1. En el servidor front-end de Skype empresarial Server 2019, abra la topología existente en Topology Builder. 
    
2. En el panel izquierdo, vaya al nodo del sitio, que se encuentra justo debajo **de Skype empresarial Server**.
    
3. Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.
    
4. En el panel izquierdo, seleccione **Ruta de federación**. 
    
5. En **asignación de ruta de Federación del sitio**, desactive la casilla **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado. 
  
6. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
7. En **generador de topologías**, seleccione el nodo superior de **Skype empresarial Server**.
    
8. En el menú **Acción**, haga clic en **Publicar topología**.
    
9. Haga clic en **siguiente** para completar el proceso de publicación y, a continuación, haga clic en **Finalizar** cuando se haya completado el proceso de publicación. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar el servidor perimetral como servidor perimetral no federado

1. En el panel izquierdo, vaya al nodo instalación heredada y, a continuación, al nodo grupos de servidores **perimetrales** . 
    
2. Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel izquierdo. 
    
4. Desactive la casilla de verificación **Habilitar la Federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página. 
  
5. En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.
    
6. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente. 
    
7. Compruebe que la Federación del servidor perimetral heredado está deshabilitada en el generador de topologías.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados en el servidor perimetral heredado

1. Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral heredado. 
    
2. En el servidor perimetral de Skype empresarial Server 2019 e importe el certificado externo del servidor proxy de acceso del paso anterior.
    
3. Asigne el certificado externo del proxy de acceso a la interfaz externa de Skype empresarial Server 2019 del servidor perimetral.
    
4. El certificado de interfaz interno del servidor perimetral de Skype empresarial Server 2019 debe solicitarse a una entidad de certificación de confianza y asignarse. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para cambiar la ruta de Federación de la versión anterior para usar el servidor perimetral de Skype empresarial Server 2019

1. En generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al nodo grupos de servidores **perimetrales** . 
    
2. Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.
    
3. Seleccione **General** en el panel izquierdo. 
    
4. Active la casilla habilitar la **Federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, haga clic en **Aceptar** para cerrar la página. 
  
5. En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.
    
6. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente. 
    
7. Compruebe que la **Federación (puerto 5061)** esté **habilitada** en el generador de topologías.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para actualizar el próximo salto de la Federación del servidor perimetral de Skype empresarial Server 2019

1. En generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al nodo grupos de servidores **perimetrales** . 
    
2. Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**. 
    
3. En la página **General** , en **selección**de próximo salto, seleccione en la lista desplegable el grupo de servidores de Skype empresarial Server 2019.
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. En **generador de topologías**, seleccione el nodo superior de **Skype empresarial Server**. 
    
6. En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar la ruta de medios de salida del servidor perimetral de Skype empresarial Server 2019

1. En el generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al grupo de servidores que se encuentra debajo de **servidores front-end Standard Edition** o **grupos de servidores front-end Enterprise Edition**.
    
2. Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.
    
3. En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**. 
  
4. En el cuadro desplegable, seleccione el servidor perimetral de Skype empresarial Server 2019.
    
5. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para activar la Federación del servidor perimetral de Skype empresarial Server 2019

1. En generador de topologías, en el panel izquierdo, vaya al nodo **Skype empresarial Server 2019** y, a continuación, al nodo grupos de servidores **perimetrales** . 
    
2. Expanda el nodo, haga clic con el botón secundario en el servidor perimetral mostrado y, a continuación, haga clic en **Editar propiedades**. 
    
    > [!NOTE]
    > La Federación solo se puede habilitar para un único grupo de servidores perimetrales. Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación. 
  
3. En la página **General** , compruebe que la casilla de verificación **Habilitar la Federación para este grupo de servidores perimetrales (puerto 5061)** está seleccionada. 
  
4. Haga clic en **Aceptar** para cerrar la página Editar propiedades. 
    
5. Navegue hasta el nodo del sitio. 
    
6. Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.
    
7. En el panel izquierdo, haga clic en **Ruta de federación**.
    
8. En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Skype empresarial Server 2019 que aparece en la lista. 
  
9. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**. 
    
     Para las implementaciones en varios sitios, complete este procedimiento en cada sitio. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar cambios de configuración en el servidor perimetral

1. En **generador de topologías**, seleccione el nodo superior de **Skype empresarial Server**. 
    
2. En el menú **Acción**, seleccione **Publicar topología** y complete el asistente. 
    
3. Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.
    
    > [!NOTE]
    > Es posible que vea el siguiente mensaje de error: **ADVERTENCIA: la topología contiene más de un servidor perimetral federado. Esto puede ocurrir durante la migración a una versión más reciente del producto. En ese caso, solo se usaría un servidor perimetral de forma activa para la Federación. Compruebe que el registro SRV de DNS externo apunte al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de Federación de manera simultánea (es decir, no es un escenario de migración), compruebe que todos los socios federados usan Skype empresarial Server. Compruebe que el registro SRV de DNS externo muestre todos los servidores perimetrales habilitados para la Federación.** Se espera que aparezca esta advertencia y se puede omitir con toda seguridad. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar el servidor perimetral de Skype empresarial Server 2019

1. Conecte todos los servidores perimetrales de Skype empresarial Server 2019. 
    
2. Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Skype empresarial Server 2019, en lugar del servidor perimetral heredado.
    
    > [!NOTE]
    > Si no dispone de un equilibrador de carga de hardware, debe actualizar el registro a de DNS para que la Federación se resuelva en el nuevo servidor perimetral de acceso de Skype empresarial Server. Para lograr esto con una interrupción mínima, reduzca el valor de TLL para el FQDN del servidor perimetral de acceso de Skype empresarial Server externo de modo que, cuando se actualice el DNS para que apunte al nuevo servidor perimetral de acceso de Skype empresarial Server, la Federación y el acceso remoto se actualizarán rápidamente. 
  
3. Detenga el **servidor perimetral de acceso de Skype empresarial Server** de cada equipo servidor perimetral. 
    
4. Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.
    
5. En la lista de servicios, busque **servidor perimetral de acceso de Skype empresarial Server**.
    
6. Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio. 
    
7. Establezca el Tipo de inicio en **Deshabilitado**. 
    
8. Haga clic en **Aceptar** para cerrar la ventana **Propiedades**. 
    

