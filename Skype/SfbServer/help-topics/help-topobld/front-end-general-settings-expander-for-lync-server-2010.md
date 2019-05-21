---
title: Expansor de configuración general front-end para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Para editar las propiedades del servidor front-end o del grupo front-end, edite o configure los siguientes atributos. La página de configuración se divide en las siguientes secciones:'
ms.openlocfilehash: b0ee8a2d0081d937bf93d4a638e4f56b1cc79134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284406"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración general front-end para Lync Server 2010

Para editar las propiedades del servidor front-end o del grupo front-end, edite o configure los siguientes atributos. La página de configuración se divide en las siguientes secciones:

 **General**

- **FQDN**: el nombre de dominio completo del servidor front-end o del grupo de servidores front-end.

- Seleccione **usar todas las direcciones IP** configuradas para usar todas las direcciones configuradas en el servidor front-end o en el grupo front-end.

    > [!IMPORTANT]
    > No debe seleccionar esta opción si Collocate el servidor de mediación en el servidor front-end o en el grupo front-end. Los servidores de mediación y los servidores front-end necesitan direcciones IP dedicadas en las que comunicarse.

- Seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba la dirección IP de la **dirección IP principal** de la comunicación del servidor front-end o del grupo de servidores front-end con el resto de la implementación. Escriba la **dirección IP de RTC** la dirección IP asociada con el servidor de mediación.

    **Características y funciones**

- **Conferencias**: Active la casilla si quiere características de conferencia en su implementación. Las conferencias incluyen audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y conferencias por Internet. Tendrá que crear y asociar un servidor de Office Web Apps para las conferencias web (definido más adelante en esta página de propiedades).

- Si selecciona conferencias, se pueden seleccionar **conferencias de acceso telefónico local (RTC)** . Seleccione la casilla para habilitar las características de conferencia de acceso telefónico local.

- Active la casilla **voz empresarial** si tiene previsto implementar características para habilitar Lync Server 2013 para que actúe como sistema de voz telefónica usando las tecnologías de voz sobre IP (VoIP), entre las que se incluyen la opción de implementar teléfonos de telefonía, troncos SIP o pública Conectividad de red telefónica conmutada usando el servidor de mediación, las puertas de enlace RTC e IP-PBX, en forma combinada o independiente, en función del diseño y los requisitos. Para obtener información detallada sobre la telefonía IP empresarial, consulte la [telefonía IP empresarial](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) y el [plan de telefonía IP empresarial en Skype empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Asociaciones**

- **Almacén de SQL Server**: el FQDN de SQL Server (y, opcionalmente, una instancia con nombre) asociada al servidor front-end o al grupo de servidores front-end. Para seleccionar el almacén SQL Server de la lista o para crear un nuevo almacén de SQL Server, haga clic en **nuevo**

- **Almacén de archivos**: seleccione el nombre completo del servidor y el recurso compartido (en el `\\<FQDN of server>\<share name>`formato) que actuará como la ubicación del almacén de archivos para los archivos compartidos que el Lync Server 2013 crea y usa para la replicación, los directorios de conferencia y otros propósitos. Para seleccionar el almacén de archivos de la lista o crear un nuevo almacén de archivos, haga clic en **nuevo**.

- Seleccione la casilla **asociar servidor** de archivado para habilitar un servidor de archivado para este servidor front-end o grupo de servidores front-end. Después de activar la casilla, seleccione un servidor de archivado existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de archivado.

- Seleccione la casilla de verificación **asociar servidor de supervisión** para habilitar un servidor de supervisión para este servidor front-end o grupo de servidores front-end. Después de seleccionar la casilla, seleccione un servidor de supervisión existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de supervisión.

- Seleccione la casilla **asociar grupo perimetral (para componentes multimedia** para habilitar un servidor perimetral para este servidor front-end o grupo de servidores front-end. Después de seleccionar la casilla, seleccione un servidor perimetral o un grupo existente de la lista o haga clic en **nuevo** para crear las definiciones para un nuevo servidor perimetral o un grupo de servidores.

  **Resistencia**

- Active la casilla de verificación grupo de registro de la **copia de seguridad asociado** para seleccionar de la lista un servidor front-end o un grupo de servidores front-end que será el registrador de la copia de seguridad (es decir, el servidor front-end o el grupo de servidores front-end designado como registrador secundario en el caso de que el principal pasa

- Si seleccionó un grupo de registro de copia de seguridad asociado y ha elegido un registrador de copia de seguridad, puede activar la casilla de verificación de **conmutación por error automática y la conmutación por error para voz**. Ahora puede definir propiedades numéricas para la detección de la **conmutación por error de voz interna (SEC)** y **intervalo de failback de voz (s)**. Para obtener más información, consulte [planificación de la resistencia de telefonía IP empresarial](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Servicios Web**

- Para configurar los **servicios Web internos**, debe definir los **puertos de escucha** para **http** y **https**. De forma predeterminada, son el puerto TCP 80 y el puerto TCP 443, respectivamente. También puede configurar los **puertos publicados** para **http** y **https**. De forma predeterminada, son el puerto TCP 80 y el puerto TCP 443, respectivamente. Según la configuración de los servicios Web internos y el uso de los equilibradores de carga (equilibradores de carga de hardware y equilibrio de carga de DNS), ajuste los valores del puerto para definir los puertos de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Los servicios Web internos y los puertos de escucha y publicación definidos son para clientes y dispositivos internos. Los clientes y dispositivos externos usan los puertos de escucha y los puertos publicados externos, junto con el nombre de dominio completo (FQDN) del servicio Web externo definido.

- Para configurar los **servicios web externos**, debe definir los **puertos de escucha** para **http** y **https**. De forma predeterminada, son el puerto TCP 80 y el puerto TCP 443, respectivamente. También puede configurar los **puertos publicados** para **http** y **https**. De forma predeterminada, son el puerto TCP 80 y el puerto TCP 443, respectivamente. Según la configuración de los servicios Web internos y el uso de los equilibradores de carga (equilibradores de carga de hardware y equilibrio de carga de DNS), ajuste los valores del puerto para definir los puertos de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Los servicios web externos y los puertos de escucha y publicación definidos son para clientes y dispositivos externos. Los clientes y dispositivos externos usan los puertos de escucha y los puertos publicados del servicio Web externo, que normalmente define el proxy inverso junto con el nombre de dominio completo (FQDN) del servicio Web externo definido. La relación del FQDN de los servicios web externos y las direcciones URL simples define las direcciones del localizador uniforme de recursos (URL) que los clientes externos usarán para acceder a los servicios disponibles para los usuarios y dispositivos externos. Para obtener más detalles sobre direcciones URL simples, consulte [planificación de direcciones URL simples](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Servidor de mediación**

- Para configurar las propiedades del **servidor** de mediación para un servidor de mediación en cola (es decir, un servidor de mediación implementado en el servidor front-end o en el grupo de servidores front-end), seleccione **servidor**de mediación agrupado.

- Para definir los **puertos de escucha** de un servidor de mediación, escriba el valor de puerto **TCP** y **TLS** que está escuchando el servidor de mediación. De forma predeterminada, TLS se define como el puerto TCP 5067.

- Para definir un valor de puerto TCP para el servidor de mediación, active la casilla **Habilitar puerto TCP** . De forma predeterminada, el servidor de mediación usa la seguridad de la capa de transporte (TLS) sobre el protocolo TCP. Los puertos TCP solo están disponibles cuando la opción Habilitar puerto TCP está habilitada.

    > [!NOTE]
    > Esta es una configuración opcional y debe consultar los requisitos de la puerta de enlace o de la RTC para determinar si lo necesita. El valor de este puerto es 5068 de forma predeterminada.

- Usted define los troncos asociados con el servidor de mediación que se encuentra. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.

    Si tiene más de una puerta de enlace asociada con un servidor de mediación, puede especificar la puerta de enlace predeterminada seleccionando la puerta de enlace que desee establecer como predeterminada y haciendo clic en **establecer como predeterminado**. Si decide quitar la puerta de enlace predeterminada actual, seleccione la puerta de enlace y haga clic en **Deshacer predeterminada**.

> [!IMPORTANT]
> Si realiza cambios en las propiedades de este cuadro de diálogo, debe publicar la topología y ejecutar el Asistente para la implementación de Skype empresarial Server en todos los servidores afectados. Después de publicar la nueva topología, se proporcionará una lista de los servidores afectados en los que debe ejecutarse el Asistente para la implementación de Skype empresarial Server como un vínculo en la pantalla de Resumen de publicación de topología correcta. Para obtener más información sobre la publicación de la topología actualizada, consulte [publicar la](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)topología. Para obtener más información sobre el Asistente para la implementación de Skype empresarial Server, consulte [herramientas administrativas de Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Haga clic en **Aceptar** para guardar y confirmar los cambios en el documento de topología.

Haga clic en **Cancelar** para descartar los cambios y cerrar las **propiedades de edición** del servidor front-end o del grupo front-end.

Haga clic en **ayuda** para leer este tema de ayuda.

## <a name="see-also"></a>Vea también

[Definir y configurar un grupo de servidores front-end o un servidor Standard Edition](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
