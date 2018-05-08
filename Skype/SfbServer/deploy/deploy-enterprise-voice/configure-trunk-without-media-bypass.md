---
title: Configurar un tronco sin omisión de medios en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Resumen: Configurar un tronco sin desvío de medios habilitado para Skype para Business Server 2015.'
ms.openlocfilehash: 1885ef2a599398fa0ef9d36075d80e0a9f588dd5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server-2015"></a>Configurar un tronco sin omisión de medios en Skype Empresarial Server 2015
 
**Resumen:** Configurar un tronco sin desvío de medios habilitado para Skype para Business Server 2015.
  
Si desea configurar un tronco con la omisión de medios deshabilitada, siga estos pasos. Si desea configurar un tronco con desvío de medios habilitado, vea [Configure un tronco con medios desvío en Skype para Business Server 2015](configure-trunk-with-media-bypass.md).
  
Tal como se describe a continuación, una configuración de tronco agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se usa para adaptar una configuración de tronco específica a un único tronco.
  
### <a name="to-configure-a-trunk-without-media-bypass"></a>Para configurar un tronco sin omisión de medios

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
    
3. En la página **Configuración del tronco**, use uno de los métodos siguientes para configurar un tronco:
    
   - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.
    
   - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
    
   - **Tronco del sitio**: elija el sitio para esta configuración de tronco en **Seleccionar un sitio**y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, este no aparecerá en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
    
   - **Tronco de grupo de servidores**: elija el nombre del tronco al que se aplica esta configuración de tronco en  **Seleccionar un servicio** y haga clic en **Aceptar**. Este tronco puede ser el tronco raíz o cualquier troncos adicionales definidas en el generador de topología. Tenga en cuenta que si ya se ha creado una configuración para un tronco específico, dicho tronco no aparecerá en **Seleccionar un servicio**.
    
    > [!NOTE]
    > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar. > El campo **nombre** está rellenado previamente con el nombre de sitio de la configuración del tronco o servicio asociado y no se puede cambiar.
  
4. Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:
    
   - **Obligatorio**: es preciso usar un cifrado de protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o la central de conmutación (PBX).
    
   - **Opcional**: se usará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    
   - **No admitido**: el proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá usar.
    
5.  Asegúrese de que esté desactivada la casilla **Habilitar omisión de medios**.
    
6. Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace de red telefónica conmutada [RTC] donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios bien conocido, desactive esta casilla.
    
7. Si el par de tronco admite la recepción de solicitudes SIP REFER desde el servidor de mediación, active la casilla de verificación **Habilitar el envío de hacer referencia a la puerta de enlace** .
    
8. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de la RTC a esta configuración de tronco. Para todas las llamadas entrantes a través del tronco que no se origina desde un Skype para extremo Business Server se aplicarán los usos de RTC asociados a esta configuración de tronco. Para administrar registros de uso de la RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    
   - Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    
   - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.
    
   - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:
    
     a. Haga clic en **Nuevo**.
    
     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
    
     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.
  
     c. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
     - Para seleccionar una o varias rutas de la lista de todas las rutas disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**. 
    
     - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
    
     - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para profesionales de 2015](create-or-modify-a-voice-route.md).
    
     - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.
    
     d. Haga clic en **Aceptar**.
    
   - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:
    
    a. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
    
    b. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
    
     - Para seleccionar una o varias rutas de la lista de todas las rutas disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**. 
    
     - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
    
     - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para profesionales de 2015](create-or-modify-a-voice-route.md).
    
     - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.
    
    c. Haga clic en **Aceptar**.
    
     > [!IMPORTANT]
     > Es importante asociar los registros de uso de RTC según el mismo nivel de servidor de mediación que está asociado el tronco que se está configurando. Si el par de servidor de mediación es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no está asociada a un registro de uso de RTC que enruta a un destino de RTC o cualquier otros sistemas indirectos conectado a través de Skype para Business Server. 
  
9. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, seleccione el registro de uso de RTC y haga clic en arriba o flecha abajo.
    
    > [!IMPORTANT]
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Skype para Business Server recorre la lista de arriba a abajo. 
  
10. Debe seleccionar la opción **Habilitar cierre RTP** para habilitar la omisión de medios para los clientes que se encuentren detrás de un firewall o NAT y para los SBC que admitan el cierre.
    
11. Debe seleccionarse **Habilitar el historial de llamadas** para habilitar el envío de información del historial de llamadas para el mismo nivel de puerta de enlace del servidor de mediación.
    
12. **Habilitar reenvío de datos P-Asserted-Identity** debe seleccionarse para habilitar la información de autor de llamada PAI se transfieran entre el servidor de mediación y la puerta de enlace (y viceversa), cuando la presentación.
    
13. Debe seleccionarse **Habilitar temporizador de conmutación por error del enrutamiento de salida** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. Reenrutamiento a otra tronco, se producirá si no se recibe esta notificación por el servidor de mediación. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.
    
14. (Opcional) Asocie y configure las **Reglas de traducción de números de llamada** para el tronco. Estas reglas de conversión se aplican al número desde donde se realizó la llamada (para las llamadas salientes).
    
   - Para elegir una o varias reglas de una lista de todas las reglas de conversión que están disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
   - Par definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener información detallada acerca de las reglas de conversión, vea [reglas de conversión de Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).
    
   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. 
    
   - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. 
    
   - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Quitar**.
    
     > [!CAUTION]
     > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto. 
  
15. (Opcional) Asocie y configure **Reglas de traducción de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.
    
   - Para elegir una o varias reglas de una lista de todas las reglas de conversión que están disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
  - Par definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener información detallada acerca de las reglas de conversión, vea [reglas de conversión de Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).
    
   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. 
    
   - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. 
    
   - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Quitar**.
    
     > [!CAUTION]
     > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto. 
  
16. Asegúrese de que las reglas de conversión del tronco se organizan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en arriba o flecha abajo.
    
    > [!IMPORTANT]
    > Skype para Business Server recorre la lista de reglas de traducción desde la parte superior hacia abajo y utiliza la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado pueda coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida con sólo los números de 11 dígitos que empiecen por + 1425, debe asegurarse de que la regla que coincide con cualquier número de 11 dígitos está ordenado *que aparece a continuación* la más restrictiva regla.
  
17. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.
    
18. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Al crear o modificar una configuración de tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicar los cambios en la configuración de enrutamiento de voz en Skype para profesionales de 2015 pendientes](voice-route-config-changes.md) en la documentación sobre operaciones.
  
## <a name="see-also"></a>Vea también

#### 

[Configurar un tronco con desvío de medios en Skype para Business Server 2015](configure-trunk-with-media-bypass.md)
#### 

[Definición de reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

