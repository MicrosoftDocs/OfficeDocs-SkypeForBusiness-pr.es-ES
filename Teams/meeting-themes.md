---
title: Temas de reunión para reuniones de Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Usar activos corporativos aprobados, como imágenes y logotipos, para crear algunos temas de reuniones personalizados para las reuniones de Teams dentro de su organización.
ms.openlocfilehash: 768c589507cac3f100d2760fe6497872a7f8ee00
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800228"
---
# <a name="meeting-themes-for-teams-meetings"></a>Temas de reunión para reuniones de Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

La personalización en las reuniones de Teams permite a las organizaciones ampliar sus identidades visuales en toda la experiencia de reunión. Las imágenes y los colores de una organización ayudan a fomentar la creación de cultura corporativa interna y aumentar el conocimiento general de la marca con los invitados. Con la ayuda de los equipos de comunicaciones corporativas y de administración de marca de una organización, los administradores de inquilinos pueden configurar y crear fácilmente temas de reuniones para varias unidades de negocio y departamentos dentro de un único inquilino.
De forma predeterminada, los usuarios con licencia premium de Teams a los que se les haya asignado una directiva de personalización de reuniones pueden crear reuniones habilitadas para temas de reuniones. Estas reuniones incluyen temas de forma predeterminada, y cualquier persona que se una a las reuniones puede ver los temas (incluidos los usuarios internos sin licencia, los invitados y los usuarios anónimos).

> [!NOTE]
> Los asistentes que se unan a Teams a través de la experiencia web no podrán ver los temas de la reunión.

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar los temas de reunión en Reuniones de Teams, compruebe que tiene los siguientes elementos:

- Acceso a la SKU de Teams Premium
- Es un administrador con acceso al Centro de administración de Teams o se le ha asignado una directiva de personalización
- El logotipo, [la imagen](#adding-a-custom-image) y el [color](#adding-a-custom-color) [personalizados](#adding-a-custom-logo-image) cumplen las especificaciones necesarias

## <a name="setting-up-meeting-branding"></a>Configurar la personalización de marca de reuniones

Los administradores de inquilinos pueden configurar y administrar temas de reuniones para las reuniones de Teams en el Centro de administración de Teams.

### <a name="creating-a-customization-policy"></a>Crear una directiva de personalización

Para crear temas de reunión, los administradores primero tendrán que crear una nueva directiva de personalización de reuniones o modificar su directiva existente.
Para habilitar la directiva de fondo personalizada, los administradores realizarán los pasos siguientes:

1. Abrir el Centro de administración de Teams
2. Seleccione **Reuniones** en el panel de navegación
3. En **Reuniones**, seleccione **Directivas de personalización**
4. Seleccione una directiva existente o cree una nueva
5. Dentro de la directiva elegida, vaya a la sección **Objetos visuales de reuniones personalizados**
6. Activar o desactivar la configuración **Actualmente activa** **para** habilitarla
7. Seleccione **Guardar** para habilitar los temas de reunión

> [!NOTE]
> Aunque puede obtener acceso a objetos visuales de reuniones personalizados desde la página Directivas de reunión, se recomienda acceder a él a través de directivas de personalización para evitar la navegación por las directivas predeterminadas de la organización global.

Dentro de la directiva de personalización de la reunión, los administradores pueden empezar a definir su personalización de marca creando un tema de reunión.

Los temas de reunión alojan los siguientes activos para su tema:

- Logotipo: imagen del logotipo de su organización.
- Imagen personalizada: una imagen de marca de su organización (las imágenes personalizadas no son las mismas que [los fondos de reunión personalizados](custom-meeting-backgrounds.md)).
- Color personalizado: se recomienda usar el color principal o secundario de tu marca, el que mejor complemente a tu imagen de marca y logotipo.

Para crear un tema nuevo, seleccione **Agregar tema de reunión**.

### <a name="adding-a-custom-logo-image"></a>Agregar una imagen de logotipo personalizada

Reuniones de Teams admite logotipos cuadrados que aparecen en superficies clave durante la reunión, incluida la pantalla de la sala de espera. Las imágenes del logotipo deben cumplir las relaciones de contraste de accesibilidad de Microsoft (4:5:1).

Las cargas deben cumplir los siguientes parámetros. Un administrador solo puede cargar:

- Los formatos de imagen PNG y JPEG para su logotipo.
- Una imagen del logotipo con un tamaño máximo de 5 MB.
- Imágenes del logotipo con una dimensión mínima de 576 px x 576 px.
- Solo una imagen por tema de su dispositivo.

### <a name="adding-a-custom-image"></a>Agregar una imagen personalizada

Las reuniones de Teams admiten las imágenes de una organización que desenfoca la pantalla de las reuniones y proporcionan un colorido fondo a las reuniones.

> [!NOTE]
> Estas imágenes no son las mismas que los [fondos de reunión personalizados](custom-meeting-backgrounds.md)

Las imágenes personalizadas deben cumplir las relaciones de contraste de accesibilidad de Microsoft (4:5:1) y las cargas deben seguir estos parámetros:

- Administración solo puede cargar formatos de imagen PNG y JPEG para imágenes de marca
- Administración solo puede cargar imagen de marca con un tamaño máximo de 5 MB
- Administración puede cargar una imagen de marca con las siguientes dimensiones:
  - Dimensiones mínimas: 360 px X 360 px
  - Dimensiones máximas: 2048 px X 2048 px
- Administración puede cargar un mínimo de 0 y un máximo de una imagen por tema desde su dispositivo

### <a name="adding-a-custom-color"></a>Agregar un color personalizado

Las reuniones de Teams admiten el color principal o secundario de una organización en la experiencia de reunión. Puede escribir el valor del código hexadecimal del color de su organización, que aparecerá en las superficies clave de la experiencia de reunión.

> [!NOTE]
> Para admitir los estándares de accesibilidad de Microsoft, es posible que el color final generado no coincida con el color de tu marca.

### <a name="previewing-a-meeting-theme"></a>Vista previa del tema de una reunión

Una vez que haya agregado los activos de la reunión, puede obtener una vista previa del aspecto que tendrá el tema antes de guardarlo.  Al seleccionar **Vista previa** se abrirá el cuadro de diálogo de vista previa y se mostrará el tema recién definido tanto para el escritorio como para dispositivos móviles.

### <a name="save-meeting-theme"></a>Guardar el tema de la reunión

Al seleccionar **Guardar**, el tema de la reunión se guarda automáticamente y se aplica a las reuniones. Si selecciona **Guardar y aplicar para más tarde** , se guardará el tema de la reunión, pero no se aplicará a ninguna de las reuniones. Para aplicar este tema, seleccione **Guardar** en el creador del tema de la reunión o use el botón de alternancia **Actualmente activo** en la tabla de temas de la reunión en la página de directiva de personalización.



### <a name="assigning-a-meeting-customization-policy-to-users"></a>Asignar una directiva de personalización de reunión a los usuarios

Las directivas de personalización de reuniones se pueden asignar a uno, varios o a un grupo de usuarios predefinido en su espacio empresarial. Asegúrese de que estos usuarios tienen una licencia premium de Teams para usar estas características.

- De forma predeterminada, todos los usuarios con licencia recibirán la directiva predeterminada global asignada.
- Las directivas de personalización personalizadas invalidarán el valor predeterminado global
- Solo se puede asignar una directiva de personalización a un usuario con licencia

### <a name="use-cases-for-multiple-departments-or-business-units-in-one-tenant"></a>Casos de uso para varios departamentos o unidades de negocio en un inquilino

Algunas organizaciones tienen varias unidades de negocio bajo diferentes identidades de marca dentro del mismo inquilino. En estos casos, los administradores pueden crear directivas de personalización de reuniones dedicadas a cada marca. También pueden asignar un departamento o grupo de usuarios de una unidad de negocio a una directiva específica.

#### <a name="a-use-case"></a>Un caso de uso

Contoso Ltd. tiene un único inquilino en Microsoft Teams, que contiene los perfiles de usuario de todos sus empleados en diferentes organizaciones empresariales. La compañía busca adoptar reuniones personalizadas con personalización de marca en Teams para aumentar su presencia de marca con sus clientes y fomentar una cultura corporativa interna.

Contoso tiene dos unidades de negocio (CCO) bajo su organización: Servicios técnicos de Contoso y Contoso Educación. Ambas BU tienen sus propias imágenes de marca distintas y quieren mostrar su personalización de marca durante sus reuniones internas y externas.

Para admitir este caso de uso, los administradores de inquilinos pueden crear dos directivas de personalización distintas:

- Directiva A - Servicios técnicos de Contoso - alberga el logotipo, la imagen y el color de la marca, la imagen y el color de Contoso Technical Service
- Directiva B - Contoso Education - incluye el logotipo, la imagen y el color de la marca de Contoso Education

Pueden proceder a asignar los empleados con licencia de Servicios técnicos de Contoso a la directiva A y a los empleados con licencia de Contoso Educación a la directiva B.

## <a name="where-are-meeting-themes-visible"></a>¿Dónde están visibles los temas de reunión?

Clientes admitidos:

- Cliente de escritorio
- Android (solo versiones 11 o posteriores)
- iOS

|         | Join Launcher | Unirse antes de la reunión | Sala de espera de la reunión | Región de reunión |
| :---:          |     :---:      |         :---:  |         :---:  |         :---:  |
| **Logo**   | No | Sí| Sí| Sí|
| **Imagen**     | No | Sí| Sí| Sí|
| **Color**     | Sí | Sí| Sí| Sí|

Los logotipos y las imágenes estarán disponibles para Unirse al iniciador en futuras actualizaciones.
> [!NOTE]
> La nueva experiencia de seminario web usará estas características del tema en las reuniones. La página de registro del seminario web se seguirá usando para configurar la personalización de marca del seminario web para el registro de reuniones y los correos electrónicos. Los organizadores de reuniones pueden desactivar los temas de reuniones de un seminario web si optan por no participar en Opciones de reunión. Más información sobre [la nueva experiencia de seminario web](set-up-webinars.md)

### <a name="who-can-view-a-meeting-theme"></a>Quién puede ver un tema de reunión

Aunque solo los usuarios con licencia asignados a una directiva de personalización de reuniones pueden crear reuniones habilitadas para temas de reuniones, cualquiera puede ver los temas que se aplican a una reunión. Entre estos usuarios se incluyen:

- En el espacio empresarial, Teams Premium usuarios con licencia
- Usuarios sin licencia en el espacio empresarial
- Invitado de usuarios inquilinos
- Usuarios externos
- Usuarios anónimos

### <a name="how-to-turn-off-meeting-themes-for-a-meeting"></a>Cómo desactivar los temas de una reunión

Los administradores de inquilinos pueden permitir que los organizadores de la reunión deshabilite los temas de una instancia de reunión específica. Si deshabilita los temas de reunión, la reunión volverá al tema predeterminado de Teams.

Para ofrecer a los organizadores de la reunión la capacidad de deshabilitar los temas de la reunión:

1. Vaya a la **directiva de personalización de la reunión**.
1. Cambie la configuración **"Tema de la reunión" que permite a los organizadores desactivar el tema de la reunión para reuniones específicas**.

Los organizadores de reuniones pueden desactivar los temas de la reunión de la siguiente forma:

1. Ir al menú **Opciones** de reunión de una instancia de reunión.
1. Desactivar la opción de reunión **Permitir que los organizadores desactiven el tema de la reunión**.

> [!NOTE]
>
> - Para las reuniones o series periódicas, la opción de reunión se aplicará a cada instancia de la reunión.
> - Los temas de reunión no se deshabilitarán para las reuniones que estén en curso. Para aplicar cambios, debe finalizar la llamada y reiniciar la reunión.

## <a name="best-practices-for-meeting-themes"></a>Procedimientos recomendados para temas de reuniones

- Use solo los activos de imagen oficiales de su organización. No use contenido de imagen que no le pertenezca.
- Trabaje con su equipo de marca y marketing para asegurarse de que los activos de imagen y los colores juntos siguen las directrices de marca de su organización.
- Asegúrate de que estás usando imágenes de logotipo de alta calidad, que son visibles en dispositivos de pantalla pequeñas y grandes.
- Los colores generados en la aplicación Teams pueden diferir de los colores de su marca. Este proceso se creó para garantizar que se cumplan los estándares de accesibilidad de Microsoft.
- Los usuarios con configuración de dispositivo de contraste alto no verán los temas de reunión.

### <a name="accessibility"></a>Accesibilidad

Estos son algunos puntos para garantizar que se cumplan los requisitos de accesibilidad:

- Seguir patrones y estructuras de interfaz de usuario existentes: la estructura actual y el texto de la pantalla no se están modificando con esta característica.
- Relación de contraste de imagen: los activos de imagen son necesarios para cumplir la relación de contraste de color 4:5:1.  
- Soporte de generación de color accesible: calculamos la salida de color accesible que sea la coincidencia más cercana a la entrada de color de marca al tiempo que mantenemos los estándares de accesibilidad de Microsoft  
- Compatibilidad con contraste alto: para los usuarios con la configuración de contraste alto habilitada, no se aplica la personalización de marca. Seguirán viendo la experiencia de reunión predeterminada de Teams.
- Controles de Administración de TI: los administradores de TI pueden impedir que los usuarios con problemas de accesibilidad vean la personalización de marca: 
  - Control de directiva: garantiza que no se agregan a una directiva de personalización. Este control les impedirá crear reuniones habilitadas para personalización de marca.
  - Opciones de reunión: los organizadores de la reunión pueden desactivar la personalización de marca de una reunión si un usuario con problemas de accesibilidad se unirá a la reunión.
