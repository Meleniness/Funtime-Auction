# Переопределить ванильные взрывы.
# При включении все взрывы будет просчитывать плагин.
explosion-overlap:
  tnt:
    enabled: true
    power: 4
    max-explosion-radius: 50
    blast-resistance-overlap: { }
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    drop-chances: 25
    optimize-packets: false
    break-only: [ ]
    removable-ps-regions: []
    damage-multiplier: 1.0
    optimize-drop: true
    distance-limiter: {}
    watchers: []
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
  creeper:
    enabled: true
    # если использовать -1, то будет использована сила взрыва крипера
    # Дефолтное значение 3
    # Заряженные криперы умножают силу взрыва на 2
    # если указать здесь 10, то заряженный крипер взорвётся со силой 20
    power: -1
    max-explosion-radius: 50
    blast-resistance-overlap: { }
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    drop-chances: 25
    optimize-packets: false
    break-only: [ ]
    removable-ps-regions: []
    damage-multiplier: 1.0
    optimize-drop: true
    distance-limiter: {}
    watchers: []
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
tnt's:
  tnt-tier-1:
    id: 'tnt#tier#1'
    fuse: 50
    power: 8 # сила взрыва, взрыв тнт равен 4, если переборщить то сервер ляжет из-за того что взрыв искать мобов для дамага в радиусе всего сервера.
    display-name: '<gradient:#00FFE0:#EB00FF>Динамит тир 1'
    lore:
      - '&r '
      - '&r &fОсобенности:'
      - '&r &fСила взрыва x2'
      - '&r '
    blast-resistance-overlap: { } # переопределение взрыво-устойчивости блока
    max-explosion-radius: 50 # максимальнай радиус взрыва в блоках
    replace-to: AIR # на что заменять взорванные блоки.
    ignore-humidity: false # Игнорировать "влажность" блоков. То есть динамит взорвёт сундук даже если он залит водой.
    apply-physics: true # Применять физику блоков после взрыва. (например песок должен осыпаться если под ним взорвётся блок).
    destroy-items: false # Будут ли взрываться лежащие предметы.
    disable-damage: false # Дамажить энтити?
    drop-chances: 25 # Шанс того что из взорванного блока выпадет лут.
    enchanted: true # Добавить эффект зачарования?
    entity-display-name: '<gradient:#00FFE0:#EB00FF>Динамит тир 1' # "голограмма" над активированным блоком тнт, оставь пустым чтобы убрать
    glowing: true # Наложить glow эффект на активированный тнт?
    break-only: [] # Если указать здесь блоки, то тнт сможет взорвать только их.
    # Возможен рассинхрон
    # При включении плагин берёт отправку пакетов об изменениях блоков на себя что сильно облегчает жизнь серверу.
    # Будет работать только при replace-to: AIR
    optimize-packets: false
    custom-model-data: 0
    minecart-recipe: true # можно ли скрафтить вагонетку с этим тнт?
    minecart-display-name: '<gradient:#00FFE0:#EB00FF>Вагонетка с динамитом тир 1'
    minecart-model-data: 0 # кастом model data для вагонетки с динамитом
    removable-ps-regions: # Материалы блоков регионов из ProtectionStones которые этот тнт может взорвать
      - EMERALD_ORE
    damage-multiplier: 1.0 # Укажите здесь 0.5, чтобы снизить урон на 50% или укажите 2.0, чтобы увеличить урон в два раза
    optimize-drop: true # Прежде чем заспавнить дроп плагин будет его стакать
    distance-limiter: # максимальная дистанция от тнт в которой блок может взорваться (не ванильно)
      # бса сможет взорваться только если она не дальше чем в трёх блоков от тнт.
      # blast-resistance-overlap никто не отменял ванильно у обсы слишком большая взрыво-устойчивость
      OBSIDIAN: 3
    watchers: # наблюдатели добавляют дополнительный функционал
      - id: timer # добавляет "голограмму" над блоком тнт с обратным таймером до взрыва
        name: '<gold>%d.%d' # %d.%d - <секунды>.<миллисекунды>
      - id: particles # спавнит партиклы при взрыве
        radius: 8 # радиус спавна партиклов
        particleCount: 70 # количество партиклов
        particle1: FLAME
        particle1Count: 0
        particle2: LAVA
        particle2Count: 10
    drop-anyway: # Список блоков которые должны выпасть после взрыва в 100% случаев
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
  tnt-tier-2:
    id: 'tnt#tier#2'
    fuse: 75
    power: 12 # default 4
    display-name: '<gradient:#00FFE0:#EB00FF>Динамит тир 2'
    lore:
      - '&r '
      - '&r &fОсобенности:'
      - '&r &fСила взрыва x3'
      - '&r '
    blast-resistance-overlap: { }
    max-explosion-radius: 50
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    enchanted: true
    entity-display-name: ''
    glowing: false
    drop-chances: 25
    optimize-packets: false
    custom-model-data: 0
    break-only: []
    removable-ps-regions: []
    minecart-recipe: true # можно ли скрафтить вагонетку с этим тнт?
    minecart-display-name: '<gradient:#00FFE0:#EB00FF>Вагонетка с динамитом тир 2'
    minecart-model-data: 0 # кастом model data для вагонетки с динамитом
    optimize-drop: true
    damage-multiplier: 1.0
    distance-limiter: {}
    watchers: []
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
  tnt-tier-3:
    id: 'tnt#tier#3'
    fuse: 100
    power: 16 # default 4
    display-name: '<gradient:#00FFE0:#EB00FF>Динамит тир 3'
    lore:
      - '&r '
      - '&r &fОсобенности:'
      - '&r &fСила взрыва x4'
      - '&r '
    blast-resistance-overlap: { }
    max-explosion-radius: 50
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    enchanted: true
    glowing: false
    entity-display-name: ''
    drop-chances: 25
    optimize-packets: false
    custom-model-data: 0
    break-only: []
    removable-ps-regions: []
    minecart-recipe: true # можно ли скрафтить вагонетку с этим тнт?
    minecart-display-name: '<gradient:#00FFE0:#EB00FF>Вагонетка с динамитом тир 3'
    minecart-model-data: 0 # кастом model data для вагонетки с динамитом
    optimize-drop: true
    damage-multiplier: 1.0
    distance-limiter: {}
    watchers: []
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
  tnt-tier-4:
    id: 'tnt#tier#4'
    fuse: 125
    power: 20 # default 4
    display-name: '<gradient:#00FFE0:#EB00FF>Динамит тир 4'
    lore:
      - '&r '
      - '&r &fОсобенности:'
      - '&r &fСила взрыва x5'
      - '&r &fВзрывает обсидиан'
      - '&r '
    blast-resistance-overlap:
      'OBSIDIAN': 6
    max-explosion-radius: 50
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    entity-display-name: ''
    glowing: false
    enchanted: true
    drop-chances: 25
    optimize-packets: true # включил только здесь, но вы можете включить везде или наоборот выключить, смотрите по состоянию сервера при взрыве большого количество тнт
    custom-model-data: 0
    break-only: []
    removable-ps-regions: []
    minecart-recipe: true # можно ли скрафтить вагонетку с этим тнт?
    minecart-display-name: '<gradient:#00FFE0:#EB00FF>Вагонетка с динамитом тир 4'
    minecart-model-data: 0 # кастом model data для вагонетки с динамитом
    optimize-drop: true
    damage-multiplier: 1.0
    distance-limiter: {}
    watchers: []
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
 
  tnt-lava-breaker:
    id: 'tnt#lava#breaker'
    fuse: 50
    power: 8 # default 4
    display-name: '<gradient:#00FFE0:#EB00FF>Уничтожитель лавы'
    lore:
      - '&r '
      - '&r &fОсобенности:'
      - '&r &fЗаменяет лаву на блоки обсидиана'
      - '&r &fВзрывает только лаву'
      - '&r '
    blast-resistance-overlap:
      'LAVA': 3
    max-explosion-radius: 50
    replace-to: OBSIDIAN
    ignore-humidity: true
    apply-physics: true
    destroy-items: false
    disable-damage: false
    entity-display-name: ''
    glowing: false
    enchanted: true
    drop-chances: 0
    optimize-packets: false
    custom-model-data: 0
    minecart-recipe: true # можно ли скрафтить вагонетку с этим тнт?
    minecart-display-name: '<gradient:#00FFE0:#EB00FF>Вагонетка с уничтожителем лавы'
    minecart-model-data: 0 # кастом model data для вагонетки с динамитом
    damage-multiplier: 1.0
    optimize-drop: true
    removable-ps-regions: []
    distance-limiter: {}
    watchers: []
    break-only:
      - 'LAVA'
    drop-anyway: [] # этот тнт ломает только лаву
 
  tnt-ice:
    id: 'tnt#ice'
    fuse: 50
    power: 8 # default 4
    display-name: '<gradient:#00FFE0:#EB00FF>Ледяная волна'
    lore:
      - '&r '
      - '&r &fОсобенности:'
      - '&r &fЗамораживает воду'
      - '&r '
    blast-resistance-overlap:
      'WATER': 2
    max-explosion-radius: 50
    replace-to: FROSTED_ICE
    ignore-humidity: true
    apply-physics: true
    destroy-items: false
    disable-damage: false
    entity-display-name: ''
    glowing: false
    enchanted: true
    optimize-packets: false
    custom-model-data: 0
    drop-chances: 0
    minecart-recipe: true # можно ли скрафтить вагонетку с этим тнт?
    minecart-display-name: '<gradient:#00FFE0:#EB00FF>Вагонетка с ледяной волной'
    minecart-model-data: 0 # кастом model data для вагонетки с динамитом
    damage-multiplier: 1.0
    optimize-drop: true
    removable-ps-regions: []
    distance-limiter: {}
    watchers: []
    break-only:
      - 'WATER'
      - 'BUBBLE_COLUMN'
    drop-anyway: [] # этот тнт ломает только воду
 
 # копии тнт с фт
  tnt-white:
    id: 'tnt#tierwhite'
    fuse: 120
    power: 15
    display-name: '&4[★]&c TNT - TIER &7WHITE'
    lore: []
    blast-resistance-overlap: { }
    max-explosion-radius: 50
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    drop-chances: 25
    enchanted: false
    entity-display-name: ''
    glowing: false
    break-only: []
    optimize-packets: true
    custom-model-data: 0
    minecart-recipe: false
    minecart-display-name: ''
    minecart-model-data: 0
    removable-ps-regions: []
    damage-multiplier: 1.0
    optimize-drop: true
    distance-limiter: {}
    watchers:
      - id: timer
        name: '<gold>%d.%d'
      - id: particles
        radius: 8
        particleCount: 70
        particle1: FLAME
        particle1Count: 0
        particle2: LAVA
        particle2Count: 10
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
 
  tnt-black:
    id: 'tnt#tierblack'
    fuse: 120
    power: 18
    display-name: '&4[★]&c TNT - TIER &8BLACK'
    lore: []
    blast-resistance-overlap:
      'ANCIENT_DEBRIS': 19
      'CRYING_OBSIDIAN': 19
      'OBSIDIAN': 19
      'NETHERITE_BLOCK': 19
      'ENCHANTING_TABLE': 19
    max-explosion-radius: 50
    replace-to: AIR
    ignore-humidity: false
    apply-physics: true
    destroy-items: false
    disable-damage: false
    drop-chances: 25
    enchanted: false
    entity-display-name: ''
    glowing: false
    break-only: []
    optimize-packets: true
    custom-model-data: 0
    minecart-recipe: false
    minecart-display-name: ''
    minecart-model-data: 0
    removable-ps-regions: []
    damage-multiplier: 1.0
    optimize-drop: true
    distance-limiter: {}
    watchers:
      - id: timer
        name: '<gold>%d.%d'
      - id: particles
        radius: 8
        particleCount: 70
        particle1: FLAME
        particle1Count: 0
        particle2: LAVA
        particle2Count: 10
    drop-anyway:
      - SHULKER_BOX
      - WHITE_SHULKER_BOX
      - ORANGE_SHULKER_BOX
      - MAGENTA_SHULKER_BOX
      - LIGHT_BLUE_SHULKER_BOX
      - YELLOW_SHULKER_BOX
      - LIME_SHULKER_BOX
      - PINK_SHULKER_BOX
      - GRAY_SHULKER_BOX
      - LIGHT_GRAY_SHULKER_BOX
      - CYAN_SHULKER_BOX
      - PURPLE_SHULKER_BOX
      - BLUE_SHULKER_BOX
      - BROWN_SHULKER_BOX
      - GREEN_SHULKER_BOX
      - RED_SHULKER_BOX
      - BLACK_SHULKER_BOX
