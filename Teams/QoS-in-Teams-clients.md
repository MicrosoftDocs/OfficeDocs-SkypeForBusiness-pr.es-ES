---
title: Implementar calidad de servicio (QoS) en Microsoft Teams clientes
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo usar calidad de servicio (QoS) para optimizar el tráfico de red para el Microsoft Teams escritorio.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094788"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementar calidad de servicio (QoS) en Microsoft Teams clientes

Puede usar calidad de servicio (QoS) basada en directivas dentro de la directiva de grupo para establecer el intervalo de puertos de origen para el valor DSCP predefinido en el Teams cliente. Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.

*Tabla 1. Rangos de puerto iniciales recomendados*

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
| | | | | |

Siempre que sea posible, configure la configuración de QoS basada en directivas dentro de un objeto de directiva de grupo. Los pasos siguientes son muy similares a Configurar intervalos de puertos y una directiva de calidad de servicio para sus clientes en [Skype Empresarial Server,](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)que tiene algunos detalles adicionales que pueden no ser necesarios.

Para crear una directiva de audio de QoS para equipos Windows 10 dominio, inicie sesión primero en un equipo en el que se haya instalado administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en Administración de directivas de grupo) y, a continuación, siga estos pasos:

1. En Administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **Clientes,** la nueva directiva debe crearse en la unidad organizativa Clientes.

1. Haga clic con el botón derecho en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y Vincule aquí**.

1. En el cuadro de diálogo Nuevo **GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre y, a continuación, haga clic en **Aceptar.**

1. Haga clic con el botón derecho en la directiva recién creada y, a continuación, haga clic **en Editar.**

1. En el Editor de administración de directivas de grupo, expanda Configuración del **equipo,** expanda Windows Configuración , **haga** clic con el botón derecho en **QoS** basado en directivas y, a continuación, haga clic **en Crear nueva directiva.**

1. En el **cuadro de diálogo QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva en el **cuadro** Nombre. Seleccione **Especificar valor DSCP** y establezca el valor en **46**. Deje **especificar la tasa de limitación saliente** no seleccionada y, a continuación, haga clic en **Siguiente.**

1. En la página siguiente, seleccione Solo aplicaciones con este nombre **ejecutable,** escriba el nombre **Teams.exe** y, a continuación, haga clic en **Siguiente.** Esta configuración indica a la directiva que solo priorice el tráfico que coincida desde el Teams cliente.

1. En la tercera página, asegúrese de que todas las direcciones **IP** de origen y Cualquier dirección **IP** de destino están seleccionadas y, a continuación, haga clic en **Siguiente.** Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que envió los paquetes y del equipo (dirección IP) que recibirá los paquetes.

1. En la página cuatro, seleccione **TCP y UDP** en la lista desplegable Seleccionar el protocolo que se aplica a esta directiva de **QoS.** TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son los dos protocolos de red más usados.

1. En el encabezado **Especificar el número de puerto de origen,** seleccione Desde este puerto o rango de **origen.** En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos 50000 a los puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019.** Haga clic en **Finalizar**.

1. Repita los pasos 5 a 10 para crear directivas para uso compartido de aplicaciones y vídeo, sustituyendo los valores adecuados en los pasos 6 y 10.

Las nuevas directivas que haya creado no se verán vigentes hasta que se actualice la directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata siguiendo estos pasos:

1. En cada equipo para el que quiera actualizar la directiva de grupo, abra un símbolo del sistema como administrador *(Ejecutar como administrador).*

1. En el símbolo del sistema, escriba

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Comprobar marcas dscp en el objeto directiva de grupo

Para comprobar que se han establecido los valores del objeto directiva de grupo, siga estos pasos:

1. Abrir un símbolo del sistema como administrador *(Ejecutar como administrador).*

1. En el símbolo del sistema, escriba

   ```console
   gpresult /R > gp.txt
   ```

   Esto generará un informe de GPO aplicados y lo enviará a un archivo de texto denominado *gp.txt*.

   Para obtener un informe HTML más legible denominado *gp.html*, escriba el siguiente comando:

   ```console
   gpresult /H gp.html
   ```

1. En el archivo generado, busque el título **Objetos** de directiva de grupo aplicados y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente están en la lista de directivas aplicadas.

1. Abra el Editor del Registro y vaya a

   Directivas de \_ software HKEY LOCAL \_ MACHINE de Microsoft Windows \\ \\ \\ \\ \\ QoS

   Compruebe los valores de las entradas del Registro que se muestran en la Tabla 2.

   *Tabla 2. Valores de Windows entradas del Registro para QoS*

   |          Nombre          |  Tipo  |    Datos     |
   |         :---:          | :---:  |    :---:    |
   |    Nombre de la aplicación    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP local        | REG_SZ |     \*      |
   | Longitud del prefijo de IP local | REG_SZ |     \*      |
   |       Puerto local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP remota        | REG_SZ |     \*      |
   |    Prefijo IP remoto    | REG_SZ |     \*      |
   |      Puerto remoto       | REG_SZ |     \*      |
   |     Velocidad de limitación      | REG_SZ |     -1      |
   | | | |

1. Compruebe que el valor de la entrada Nombre de aplicación es correcto para el cliente que usa y compruebe que las entradas Valor DSCP y Puerto local reflejen la configuración en el objeto Directiva de grupo.


## <a name="related-topics"></a>Temas relacionados

[Implementar calidad de servicio (QoS) en Teams](QoS-in-Teams.md)