---
title: Configurar tipos de direcciones IP en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Summary: Review the IP Address type considerations below before implementing Skype for Business Server.'
ms.openlocfilehash: ba10dd223e7e099d27e31bddce478603f50e49a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101256"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurar tipos de direcciones IP en Skype Empresarial

**Resumen:** Revise las consideraciones de tipo de dirección IP que se indican a continuación antes de implementar Skype Empresarial Server.

Los tipos de direcciones IP se implementan mediante la configuración de topología que se configura en el Generador de topologías. En esta sección se describe cómo implementar tipos de direcciones IP en servidores front-end, servidores de mediación y servidores perimetrales.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implementar tipos de direcciones IP en un servidor front-end

Con el Generador de topologías, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor front-end.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Para implementar los tipos de direcciones IP en un servidor front-end

1. En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades**. (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

2. En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**.

   **Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**

   - **Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.

     > [!NOTE]
     > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

   - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, debe introducir un valor para la **dirección IP principal**.

   - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida debe coincidir con el formato del tipo de dirección seleccionado.

   - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.

> [!NOTE]
> No se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de direcciones IP RTC (o por cualquier otro motivo) en servidores front-end. Para obtener más información acerca de las configuraciones de NIC admitidas para Skype Empresarial Server, vea Plataformas de hardware de servidor para [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implementar tipos de direcciones IP en un servidor de mediación

Con el Generador de topologías, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implementar tipos de direcciones IP en un servidor de mediación

- En el Generador de topologías, en **Grupos de servidores de mediación,** haga clic con el botón secundario en el servidor de un grupo de servidores y, a continuación, seleccione Editar **propiedades**. (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

- En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.

   **Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**

  - **Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.

    > [!NOTE]
    > Esta es la opción recomendada para las configuraciones de IP versión 6 (IPv6).

  - **Limitar el uso del servicio a las direcciones especificadas**. Seleccione esta opción para especificar una dirección concreta para usarla en el nuevo servidor. Si selecciona esta opción, debe indicar un valor de dirección IP principal.

  - **Dirección IP principal**. Escriba una dirección IP que va a utilizar el servidor para todas las comunicaciones excepto la red telefónica conmutada (RTC) pública. La dirección IP escrita debe coincidir con el formato del tipo de dirección seleccionado.

  - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.
> [!IMPORTANT]
> Solo se admiten dos tarjetas de red en *servidores de* mediación dedicados. Si el rol Servidor de mediación está situado en front-end, no se admiten tarjetas de red duales. 

> [!NOTE]
> - Para obtener más información acerca de las configuraciones de NIC compatibles para Skype Empresarial Server 2015, vea [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Para obtener más información acerca de las configuraciones de NIC compatibles para Skype Empresarial Server 2019, vea [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Implementar tipos de direcciones IP en un servidor perimetral

Con el Generador de topologías, realice los pasos siguientes:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implementar tipos de direcciones IP en un servidor perimetral

1. En el Generador de topologías, en **Grupos perimetrales,** haga clic con el botón secundario en el servidor de un grupo de servidores y, a continuación, **seleccione Editar propiedades**. (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

2. En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir.

3. Debe proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.