---
title: Ampliador de configuración General de extremo frontal para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Para editar las propiedades de la agrupación de servidor Front-End o Front-End, editar o configurar los atributos siguientes. La página de configuración se divide en las siguientes secciones:'
ms.openlocfilehash: 2e249f1bd7f0f42cdc23429d79afde86d3f175a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Ampliador de configuración General de extremo frontal para Lync Server 2010
 
Para editar las propiedades de la agrupación de servidor Front-End o Front-End, editar o configurar los atributos siguientes. La página de configuración se divide en las siguientes secciones:
  
 **General**
  
- **Nombre de dominio completo**: el nombre de dominio completo de la agrupación de servidor Front-End o Front-End.
    
- Seleccione **utilizar todas las direcciones IP configuradas** para hacer uso de todas las direcciones configuradas en el servidor Front-End o Front-End de grupo de servidores.
    
    > [!IMPORTANT]
    > No debe seleccionar esta opción si colocar el servidor de mediación en el servidor Front-End o un grupo de servidores Front-End. Servidores de mediación y servidores frontales necesitan direcciones IP dedicadas en la que desea comunicarse. 
  
- Seleccione **limitar el uso de servicio a las direcciones IP seleccionadas** y escriba la dirección IP para la **dirección IP principal** para la comunicación de grupo de servidor Front-End o Front-End con el resto de la implementación. Escriba la dirección IP que está asociada con el servidor de mediación en la **dirección IP de RTC** .
    
    **Características y funcionalidad**
    
- **Conferencias**: seleccione la casilla de verificación si desea que las características de conferencia en su implementación. Conferencia incluye audio, vídeo, uso compartido de aplicaciones, escritorio compartido y conferencias Web. Debe crear y asociar un servidor de Office Web Apps para conferencias Web (definido más adelante en esta página de propiedades).
    
- Si ha seleccionado la conferencia, puede seleccionarse **conferencing Dial-in (PSTN)** . Active la casilla de verificación para habilitar las características de conferencia de acceso telefónico.
    
- Active la casilla de verificación **De la Telefonía IP empresarial** si va a implementar características para habilitar 2013 de Lync Server actuar como el sistema de voz de teléfono mediante voz sobre tecnologías IP (VoIP), incluyendo la opción de implementar teléfonos de auricular, SIP troncos o público conectividad de red telefónica conmutada mediante IP-PBX, puertas de enlace PSTN y servidor de mediación en combinación o solos, basándose en los requisitos y el diseño. Para detalles sobre Telefonía IP empresarial, consulte [Plan para Telefonía IP empresarial en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) y [Telefonía IP empresarial](http://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)
    
    **Asociaciones**
    
- **SQL Server almacenar**: el FQDN de la de SQL Server (y, opcionalmente, una instancia con nombre) asociada con el grupo de servidor Front-End o Front-End. Seleccione el almacén de SQL Server de la lista o crear un nuevo almacén de SQL Server haciendo clic en **nuevo**
    
- **Almacenar archivo**: seleccione el FQDN del servidor y del recurso compartido (en el formato `\\<FQDN of server>\<share name>`) que actuará como la ubicación del almacén de archivo de los archivos compartidos que Lync Server 2013 crea y utiliza para replicación, directorios de conferencia y otros propósitos. Seleccione el almacén de archivos de la lista o crear un nuevo almacén de archivo haciendo clic en **nuevo**.
    
- Seleccione la casilla de verificación **Servidor de archivado de asociar** para habilitar a un servidor de archivado para este grupo de servidor Front-End o Front-End. Después de seleccionar la casilla de verificación, seleccione un servidor de archivado existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de archivado.
    
- Seleccione la casilla de **Asociar el servidor de supervisión** para habilitar a un servidor de supervisión para este grupo de servidor Front-End o Front-End. Después de seleccionar la casilla de verificación, seleccione un servidor de supervisión existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de supervisión.
    
- Seleccione el **asociar la piscina de borde (para componentes media** casilla de verificación para habilitar un servidor perimetral para este grupo de servidor Front-End o Front-End. Después de seleccionar la casilla de verificación, seleccione un servidor perimetral existente o un grupo de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor perimetral o grupo.
    
 **Resiliencia**
  
- Active la casilla de **grupo de registrador auxiliar asociada** para seleccionar en la lista grupo de servidor Front-End o Front-End que será el registrador de copia de seguridad (es decir, el servidor Front-End o Front-End el grupo designado como registrador secundario en caso de que el primario se produce un error)
    
- Si ha seleccionado grupo de registrador auxiliar asociada y ha elegido a un registrador de copia de seguridad, puede seleccionar la casilla de verificación para **automático failover y failback para voz**. Ahora puede definir propiedades numéricas para **voz failover detección interno (s)** y el **intervalo de recuperación tras error de voz (s)**. Para obtener más información, vea [Planear la resiliencia de Telefonía IP empresarial](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
    
 **Servicios Web**
  
- Para configurar **los servicios web internos**, puede definir **puertos de escucha** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. También se pueden configurar los **puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. Basándose en la configuración de servicios web interno y el uso de equilibradores de carga (equilibradores de carga hardware y equilibrio de carga DNS), ajuste los valores para definir la escucha del puerto y los puertos publicados.
    
    > [!IMPORTANT]
    > Servicios web interno y escucha definido y puertos publicados son para dispositivos y clientes internos. Dispositivos y clientes externos utilizan los servicios web externos a la escucha y publica puertos, junto con el nombre de dominio completo de servicios web externos definidos (FQDN). 
  
- Para configurar los **servicios web externos**, puede definir **puertos de escucha** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. También se pueden configurar los **puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. Basándose en la configuración de servicios web interno y el uso de equilibradores de carga (equilibradores de carga hardware y equilibrio de carga DNS), ajuste los valores para definir la escucha del puerto y los puertos publicados.
    
    > [!IMPORTANT]
    > Servicios web externos y escucha definido y puertos publicados son para dispositivos y clientes externos. Dispositivos y clientes externos utilizan los servicios web externos a la escucha y publica los puertos, normalmente definidos por el proxy inverso junto con el nombre de dominio completo de servicios web externos definidos (FQDN). La relación de los servicios web externos FQDN y las direcciones URL Simple definen las direcciones de uniform resource locator (URL) que los clientes externos se utilizará para tener acceso a los servicios disponibles para los usuarios externos y dispositivos. Para obtener más información sobre direcciones URL Simple, vea [Planear simples direcciones URL](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
 **Servidor de mediación**
  
- Para configurar propiedades del **Servidor de mediación** para un servidor de mediación colocadas (es decir, un servidor de mediación implementados en el grupo de servidor Front-End o Front-End), seleccione **servidor de mediación ubicados habilitado**.
    
- Para definir los **puertos de escucha** de un servidor de mediación colocadas, escriba el valor del puerto **TLS** y **TCP** que está escuchando el servidor de mediación colocadas. De forma predeterminada, TLS está definido como puerto TCP 5067.
    
- Para definir un valor de puerto TCP para el servidor de mediación, seleccione la casilla de verificación **Habilitar el puerto TCP** . De forma predeterminada, el servidor de mediación utiliza la seguridad de la capa de transporte (TLS) sobre el protocolo TCP. Puertos TCP sólo están disponibles cuando se habilita la selección de habilitar el puerto TCP.
    
    > [!NOTE]
    > Ésta es una configuración opcional, y se debe hacer referencia a los requisitos de la puerta de enlace o PSTN para determinar si necesita. El valor de este puerto es 5068 de forma predeterminada. 
  
- Definir los troncos que están asociados con el servidor de mediación colocadas. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.
    
    Si tiene más de una puerta de enlace asociada con un servidor de mediación, puede especificar la puerta de enlace predeterminada seleccionando la puerta de enlace que desee establecer como predeterminada y haga clic en **Establecer como predeterminado**. Si decide quitar la puerta de enlace predeterminada actual, seleccione la puerta de enlace y haga clic en **Deshacer predeterminado**.
    
> [!IMPORTANT]
> Si realiza cambios en las propiedades de este cuadro de diálogo, debe publicar la topología y ejecutar el Skype para el Asistente para implementación de Business Server en todos los servidores afectados. Después de publicar la nueva topología, se proporciona una lista de servidores afectados donde debe ejecutarse el Skype para el Asistente para implementación de Business Server para usted como un vínculo en la pantalla de resumen de publicación topología correcta. Para obtener más información sobre la publicación de la topología actualizados, consulte la [publicación de la topología](http://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Para obtener detalles sobre el Skype para el Asistente para implementación de Business Server, consulte [Herramientas administrativas de Lync Server](http://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx). 
  
Haga clic en **Aceptar** para guardar y confirmar los cambios en el documento de la topología.
  
Haga clic en **Cancelar** para descartar los cambios y cerrar el **Editar propiedades** para el grupo de servidor Front-End o Front-End.
  
Haga clic en **Ayuda** para leer este tema de ayuda.
  
## <a name="see-also"></a>Vea también

#### 

[Definir y configurar un grupo de servidores Front-End o un servidor Standard Edition](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)

