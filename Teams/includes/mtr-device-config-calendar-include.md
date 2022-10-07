
Para ayudar a los usuarios a programar reuniones más fácilmente en una sala de Teams, puede crear listas y lugares de salas en Exchange Online. 

Las listas de salones de Exchange y los lugares de Outlook se usan para controlar qué cuentas de recursos (y, por lo tanto, las Salas de Teams están asociadas) aparecen en el Buscador de salas de Outlook. El Buscador de salas es una característica de Outlook que ayuda a los usuarios a encontrar las salas que están cerca de ellas, que están disponibles para reservas y que cumplen otros criterios, como la disponibilidad de una pantalla.

Las listas de salas son un tipo especial de grupo de distribución de Exchange que le permiten agrupar las cuentas de recursos (y, por tanto, las Salas de Teams a las que están asociadas) de forma significativa. Por ejemplo, es posible que desee crear listas de salas para todas las salas de cada edificio del campus.

Outlook Places le permite establecer atributos específicos sobre una cuenta de recursos y su sala de Teams. Algunos de los atributos que puede establecer son:

- Building
- Ciudad
- Capacidad
- Si la ubicación es accesible para sillas de ruedas
- Nombres de audio, vídeo y visualización

Con una combinación de listas de salas y atributos de ubicación seleccionados por un usuario, el Buscador de salas de Outlook mostrará una lista de las salas disponibles para su reserva. Para hacer el mejor uso de las listas y los lugares de las salas, cree listas de salones basadas en un atributo de lugar, como la construcción. Por ejemplo, establezca los atributos de ciudad y lugar de creación para cada cuenta de recursos y, a continuación, agregue cada cuenta de recursos a una lista de salones de edificio. Cuando un usuario intenta elegir una sala para reservar, Outlook mostrará una lista de ciudades y las listas de salas disponibles en cada una de esas ciudades.

> [!IMPORTANT]
> Cada cuenta de recursos debe tener sus atributos de ubicación establecidos. Si estos atributos, especialmente ciudad, edificio y capacidad, no están establecidos, esas salas no se mostrarán como opciones disponibles para la reserva incluso si una lista de salas las contiene.

Para crear una lista de salas, siga las instrucciones de [Crear una lista de salas](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list).

Para configurar los atributos de ubicación para una cuenta de recursos, vea [Set-Place](/powershell/module/exchange/set-place).
