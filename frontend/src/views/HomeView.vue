<template>
  <div class="ctrip-layout">
    <!-- 顶部导航栏 -->
    <header class="top-nav">
      <div class="nav-left">
        <div class="logo">
          <span class="logo-icon">🏔️</span>
          <span class="logo-text">Outdoor Partner</span>
        </div>
        <div class="search-bar">
          <input type="text" placeholder="搜索户外装备、路线、活动" />
          <button class="search-btn">🔍</button>
        </div>
      </div>
      <div class="nav-right">
        <a href="#" class="nav-link">登录</a>
        <a href="#" class="nav-link">注册</a>
        <a href="#" class="nav-link">我的订单 </a>
        <a href="#" class="nav-link">联系客服</a>
        <span class="nav-icons">📱 💬 </span>
      </div>
    </header>

    <div class="main-body">
      <!-- 左侧菜单 -->
      <aside class="sidebar">
        <nav class="sidebar-nav">
          <a href="#" class="nav-item" :class="{ active: currentView === 'home' }" @click.prevent="currentView = 'home'">
            <span class="nav-icon">⛺</span> 露营装备
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'hiking' }" @click.prevent="currentView = 'hiking'">
            <span class="nav-icon">🥾</span> 徒步鞋服
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'backpack' }" @click.prevent="currentView = 'backpack'">
            <span class="nav-icon"></span> 背包
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'tent' }" @click.prevent="currentView = 'tent'">
            <span class="nav-icon">️</span> 帐篷
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'lighting' }" @click.prevent="currentView = 'lighting'">
            <span class="nav-icon"></span> 户外照明
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'navigation' }" @click.prevent="currentView = 'navigation'">
            <span class="nav-icon">🧭</span> 导航工具
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'cooking' }" @click.prevent="currentView = 'cooking'">
            <span class="nav-icon">🍳</span> 野炊装备
          </a>
          <a href="#" class="nav-item new-item" :class="{ active: currentView === 'ai-route' }" @click.prevent="currentView = 'ai-route'">
            <span class="nav-icon">🤖</span> AI路线规划
            <span class="badge-new">NEW</span>
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'route' }" @click.prevent="currentView = 'route'">
            <span class="nav-icon">🗺️</span> 户外路线
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'map' }" @click.prevent="currentView = 'map'">
            <span class="nav-icon">📍</span> 活动地图
          </a>
          <div class="sidebar-divider"></div>
          <a href="#" class="nav-item" :class="{ active: currentView === 'global' }" @click.prevent="currentView = 'global'">
            <span class="nav-icon"></span> 全球户外
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'member' }" @click.prevent="currentView = 'member'">
            <span class="nav-icon"></span> 会员权益
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'insurance' }" @click.prevent="currentView = 'insurance'">
            <span class="nav-icon">💰</span> 户外保险
          </a>
          <div class="sidebar-divider"></div>
          <a href="#" class="nav-item" :class="{ active: currentView === 'team' }" @click.prevent="currentView = 'team'">
            <span class="nav-icon">👥</span> 团队活动
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'expert' }" @click.prevent="currentView = 'expert'">
            <span class="nav-icon">🏆</span> 户外达人
          </a>
          <a href="#" class="nav-item" :class="{ active: currentView === 'about' }" @click.prevent="currentView = 'about'">
            <span class="nav-icon">️</span> 关于我们
          </a>
        </nav>
      </aside>

      <!-- 主内容区 -->
      <main class="content">
        <!-- 首页内容 -->
        <div v-if="currentView === 'home'">
          <!-- 装备预订表单 -->
          <div class="hotel-booking">
            <div class="booking-header">
              <h2>预订装备</h2>
              <div class="booking-tags">
                <span class="tag安心订">品质保证</span>
                <span class="tag放心住">专业推荐</span>
              </div>
            </div>
            <div class="booking-form">
              <div class="form-row">
                <div class="form-group">
                  <label>目的地/装备名称</label>
                  <input type="text" value="川西高原" />
                </div>
                <div class="form-group date-group">
                  <label>出发日期</label>
                  <div class="date-input">
                    <span>10月26日 (今天)</span>
                    <span class="nights">3天</span>
                    <span>10月28日 (后天)</span>
                  </div>
                </div>
                <div class="form-group">
                  <label>返回日期</label>
                  <input type="text" value="10月28日 (后天)" />
                </div>
              </div>
              <div class="form-row">
                <div class="form-group">
                  <label>人数</label>
                  <select>
                    <option>1人</option>
                  </select>
                </div>
                <div class="form-group">
                  <label>装备类型</label>
                  <select>
                    <option>不限</option>
                  </select>
                </div>
                <div class="form-group keyword-group">
                  <label>关键词(选填)</label>
                  <input type="text" placeholder="帐篷/睡袋/登山杖..." />
                </div>
                <button class="search-hotel-btn"> 搜索</button>
              </div>
            </div>
          </div>

          <!-- 广告横幅 -->
          <div class="promo-banner">
            <div class="promo-content">
              <span class="promo-tag">户外装备节</span>
              <div class="promo-text">
                <h3>专业登山装备套装</h3>
                <p>秋冬户外季 全套装备899元起 ➤</p>
              </div>
            </div>
          </div>

          <!-- AI路线规划 & 活动地图 -->
          <div class="quick-links">
            <div class="quick-link-item">
              <span class="ql-icon">🤖</span>
              <div class="ql-text">
                <strong>AI路线规划</strong>
                <span>智能定制您的户外之旅 ➤</span>
              </div>
            </div>
            <div class="quick-link-item">
              <span class="ql-icon">🗺️</span>
              <div class="ql-text">
                <strong>活动地图</strong>
                <span>发现·好去处 ➤</span>
              </div>
            </div>
          </div>

          <!-- 装备推荐 -->
          <div class="hotel-recommend">
            <div class="section-header">
              <h3>装备<span class="highlight">推荐</span></h3>
              <div class="city-tabs">
                <button class="city-tab active">徒步</button>
                <button class="city-tab">露营</button>
                <button class="city-tab">攀岩</button>
                <button class="city-tab">滑雪</button>
                <button class="city-tab">更多 ▾</button>
              </div>
            </div>
            <div class="hotel-cards">
              <div class="hotel-card" v-for="hotel in hotels" :key="hotel.id">
                <div class="hotel-img" :style="{ backgroundColor: hotel.color }">
                  <span class="hotel-img-text">{{ hotel.imgText }}</span>
                  <span class="ad-tag" v-if="hotel.isAd">推荐</span>
                </div>
                <div class="hotel-info">
                  <h4>{{ hotel.name }}</h4>
                  <div class="hotel-rating">
                    <span class="rating-score">{{ hotel.score }}</span>
                    <span class="rating-label">优秀</span>
                    <span class="rating-review">{{ hotel.reviews }}条评价</span>
                  </div>
                  <div class="hotel-price">
                    <span class="original-price" v-if="hotel.originalPrice">¥{{ hotel.originalPrice }}</span>
                    <span class="current-price">¥{{ hotel.price }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- 当季热推 -->
          <div class="seasonal-recommend">
            <div class="section-header">
              <h3>当季<span class="highlight">热推</span></h3>
              <div class="departure-select">
                <span>出发地</span>
                <select>
                  <option>成都</option>
                </select>
              </div>
            </div>
            <div class="seasonal-grid">
              <!-- 热门路线 -->
              <div class="seasonal-block tour-block">
                <div class="block-header">
                  <span class="block-icon">🥾</span>
                  <h4>当季热卖·热门路线 ➤</h4>
                </div>
                <div class="tour-list">
                  <div class="tour-item" v-for="tour in tours" :key="tour.id">
                    <span class="tour-rank" :class="'rank-' + tour.rank">{{ tour.rank }}</span>
                    <div class="tour-img" :style="{ backgroundColor: tour.color }"></div>
                    <div class="tour-info">
                      <div class="tour-name">{{ tour.name }}</div>
                      <div class="tour-meta">
                        <span class="tour-score">{{ tour.score }}分</span>
                        <span class="tour-count">{{ tour.count }}人参与</span>
                      </div>
                    </div>
                    <div class="tour-price">¥{{ tour.price }}起</div>
                  </div>
                </div>
              </div>
              <!-- 特价装备 -->
              <div class="seasonal-block flight-block">
                <div class="block-header">
                  <span class="block-icon"></span>
                  <h4>周末特惠·精选装备 ➤</h4>
                </div>
                <div class="flight-list">
                  <div class="flight-item" v-for="flight in flights" :key="flight.id">
                    <span class="flight-rank" :class="'rank-' + flight.rank">{{ flight.rank }}</span>
                    <div class="flight-img" :style="{ backgroundColor: flight.color }"></div>
                    <div class="flight-info">
                      <div class="flight-route">{{ flight.from }} - {{ flight.to }}</div>
                      <div class="flight-tag">{{ flight.tag }}</div>
                      <div class="flight-date">{{ flight.date }}</div>
                    </div>
                    <div class="flight-price-area">
                      <div class="flight-price">¥{{ flight.price }}起</div>
                      <div class="flight-discount">{{ flight.discount }}</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- 导航工具界面 -->
        <div v-if="currentView === 'navigation'" class="navigation-page">
          <!-- 导航搜索模块 -->
          <div class="navigation-search">
            <div class="search-header">
              <h2>智能导航</h2>
              <div class="search-tags">
                <span class="tag-safe" :class="{ active: navMode === 'safe' }" @click="navMode = 'safe'">🛡️ 安全路线</span>
                <span class="tag-fast" :class="{ active: navMode === 'fast' }" @click="navMode = 'fast'">⚡ 最快速度</span>
              </div>
            </div>
            <div class="search-form">
              <div class="form-row">
                <div class="form-group">
                  <label>起点位置</label>
                  <div class="point-input">
                    <span class="point-dot start"></span>
                    <input type="text" v-model="navForm.start" placeholder="输入起点" />
                    <button class="swap-btn" title="交换起终点" @click="swapPoints">⇅</button>
                  </div>
                </div>
                <div class="form-group">
                  <label>目的地</label>
                  <div class="point-input">
                    <span class="point-dot end"></span>
                    <input type="text" v-model="navForm.destination" placeholder="输入目的地名称" @keyup.enter="startNavigation" />
                  </div>
                </div>
                <div class="form-group">
                  <label>路线类型</label>
                  <select v-model="navForm.routeType">
                    <option>徒步路线</option>
                    <option>骑行路线</option>
                    <option>自驾路线</option>
                    <option>越野跑路线</option>
                  </select>
                </div>
              </div>
              <div class="form-row">
                <div class="form-group">
                  <label>难度等级</label>
                  <select v-model="navForm.difficulty">
                    <option>不限</option>
                    <option>初级</option>
                    <option>中级</option>
                    <option>高级</option>
                  </select>
                </div>
                <div class="form-group">
                  <label>预计时长</label>
                  <select v-model="navForm.duration">
                    <option>不限</option>
                    <option>1-2小时</option>
                    <option>3-4小时</option>
                    <option>半天</option>
                    <option>全天</option>
                    <option>多日穿越</option>
                  </select>
                </div>
                <button class="search-route-btn" @click="startNavigation">开始导航</button>
              </div>
            </div>
            <!-- 路线规划结果 -->
            <transition name="fade">
              <div class="route-result" v-if="plannedRoute">
                <div class="result-summary">
                  <div class="result-item">
                    <span class="result-value">{{ plannedRoute.distance }}</span>
                    <span class="result-label">总里程</span>
                  </div>
                  <div class="result-item">
                    <span class="result-value">{{ plannedRoute.duration }}</span>
                    <span class="result-label">预计耗时</span>
                  </div>
                  <div class="result-item">
                    <span class="result-value">{{ plannedRoute.climb }}</span>
                    <span class="result-label">累计爬升</span>
                  </div>
                  <div class="result-item">
                    <span class="result-value">{{ plannedRoute.calories }}</span>
                    <span class="result-label">消耗(千卡)</span>
                  </div>
                  <div class="result-item">
                    <span class="result-value level-text">{{ plannedRoute.level }}</span>
                    <span class="result-label">难度评估</span>
                  </div>
                </div>
                <div class="result-waypoints">
                  <span class="wp-label">途经点：</span>
                  <span class="wp-item" v-for="(wp, i) in plannedRoute.waypoints" :key="i">
                    {{ wp }}<em v-if="i < plannedRoute.waypoints.length - 1"> → </em>
                  </span>
                </div>
              </div>
            </transition>
          </div>

          <!-- 地图显示区 -->
          <div class="map-container">
            <div class="map-toolbar">
              <div class="layer-tabs">
                <button
                  v-for="layer in mapLayers"
                  :key="layer.key"
                  class="layer-tab"
                  :class="{ active: mapLayer === layer.key }"
                  @click="mapLayer = layer.key"
                >{{ layer.label }}</button>
              </div>
              <span class="map-coord">📍 {{ mockCoord }} | 海拔 {{ mockAltitude }}m</span>
            </div>
            <div class="map-canvas" :class="'layer-' + mapLayer">
              <div class="map-grid"></div>
              <!-- 模拟路线 -->
              <svg class="map-route" viewBox="0 0 600 300" preserveAspectRatio="none">
                <path d="M 80 240 C 160 200, 180 120, 280 130 S 430 80, 520 60" fill="none" stroke="#2577e3" stroke-width="4" stroke-dasharray="10 6" stroke-linecap="round" />
              </svg>
              <span class="map-marker marker-start" style="left: 10%; top: 76%;">起</span>
              <span class="map-marker marker-end" style="left: 84%; top: 14%;">终</span>
              <div class="zoom-controls">
                <button @click="mapZoom = Math.min(mapZoom + 1, 18)" title="放大">＋</button>
                <span class="zoom-level">{{ mapZoom }}</span>
                <button @click="mapZoom = Math.max(mapZoom - 3, 3)" title="缩小">－</button>
              </div>
              <button class="locate-btn" title="定位到当前位置">◎</button>
              <div class="map-scale">︙ {{ scaleText }}</div>
            </div>
            <div class="map-controls">
              <button
                v-for="ctrl in mapControls"
                :key="ctrl.key"
                class="control-btn"
                :class="{ active: activeMapTool === ctrl.key }"
                @click="toggleMapTool(ctrl.key)"
              >{{ ctrl.icon }} {{ ctrl.label }}</button>
            </div>
          </div>

          <!-- 热门路线推荐 -->
          <div class="popular-routes">
            <div class="section-header">
              <h3>热门<span class="highlight">路线</span></h3>
              <div class="route-tabs">
                <button
                  v-for="tab in routeTabs"
                  :key="tab.key"
                  class="route-tab"
                  :class="{ active: activeRouteTab === tab.key }"
                  @click="activeRouteTab = tab.key"
                >{{ tab.label }}</button>
              </div>
            </div>
            <div class="route-cards">
              <div class="route-card" v-for="route in filteredRoutes" :key="route.id">
                <div class="route-img" :style="{ backgroundColor: route.color }">
                  <span class="route-img-text">{{ route.name }}</span>
                  <span class="difficulty-badge" :class="'level-' + route.difficulty">
                    {{ route.difficultyText }}
                  </span>
                  <button class="fav-btn" :class="{ faved: route.favorite }" @click.stop="route.favorite = !route.favorite" title="收藏">
                    {{ route.favorite ? '★' : '☆' }}
                  </button>
                </div>
                <div class="route-info">
                  <h4>{{ route.name }}</h4>
                  <div class="route-tags">
                    <span class="route-tag" v-for="t in route.tags" :key="t">{{ t }}</span>
                  </div>
                  <div class="route-stats">
                    <span class="stat-item">📏 {{ route.distance }}</span>
                    <span class="stat-item">⏱️ {{ route.duration }}</span>
                    <span class="stat-item">⛰️ {{ route.elevation }}</span>
                  </div>
                  <div class="route-bottom">
                    <div class="route-rating">
                      <span class="rating-score">{{ route.score }}</span>
                      <span class="rating-count">{{ route.reviews }}条评价</span>
                    </div>
                    <button class="route-nav-btn" @click="goRoute(route)">去导航</button>
                  </div>
                </div>
              </div>
              <div class="route-empty" v-if="filteredRoutes.length === 0">
                <p>暂无收藏路线，点击卡片右上角 ☆ 收藏喜欢的路线吧</p>
              </div>
            </div>
          </div>

          <!-- 导航工具集 -->
          <div class="tools-section">
            <div class="section-header">
              <h3>导航<span class="highlight">工具集</span></h3>
              <span class="tools-count">共 {{ tools.length }} 个工具</span>
            </div>
            <div class="tool-grid">
              <div class="tool-card" v-for="tool in tools" :key="tool.id" :class="{ disabled: tool.disabled }">
                <div class="tool-card-icon">{{ tool.icon }}</div>
                <h4>{{ tool.name }}</h4>
                <p>{{ tool.description }}</p>
                <button class="tool-use-btn" :disabled="tool.disabled" @click="tool.disabled || useTool(tool)">
                  {{ tool.disabled ? '即将上线' : '立即使用' }}
                </button>
              </div>
            </div>
          </div>
        </div>
      </main>

      <!-- 右侧栏 -->
      <aside class="right-sidebar">
        <div class="city-guide">
          <h4>川西必带装备攻略</h4>
          <div class="guide-carousel">
            <div class="carousel-dots">
              <span class="dot active"></span>
              <span class="dot"></span>
              <span class="dot"></span>
              <span class="dot"></span>
            </div>
          </div>
          <div class="guide-hotels">
            <div class="guide-hotel-item" v-for="gh in guideHotels" :key="gh.id">
              <div class="guide-hotel-img" :style="{ backgroundColor: gh.color }"></div>
              <div class="guide-hotel-info">
                <span>{{ gh.name }}</span>
                <span class="guide-hotel-price">¥{{ gh.price }}起</span>
              </div>
            </div>
          </div>
        </div>

        <div class="ranking-banner">
          <div class="ranking-content">
            <h4>户外榜单</h4>
            <p>解决装备选择题 ➤</p>
          </div>
        </div>

        <div class="business-banner">
          <div class="business-content">
            <h4>团队定制</h4>
            <p>Outdoor Partner 旗下一站式企业团建服务平台</p>
          </div>
        </div>
      </aside>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, computed } from 'vue'

const currentView = ref('')

const hotels = ref([
  { id: 1, name: '专业登山帐篷套装', score: '4.8', reviews: '5197', price: '1,011', originalPrice: null, color: '#4a6741', imgText: '专业帐篷套装', isAd: true },
  { id: 2, name: '轻量徒步背包60L', score: '4.9', reviews: '2488', price: '341', originalPrice: '362', color: '#5c4a3a', imgText: '轻量背包', isAd: true },
  { id: 3, name: '户外睡袋-15°C', score: '4.8', reviews: '3537', price: '597', originalPrice: null, color: '#3a4a5c', imgText: '保暖睡袋', isAd: true },
])

const tours = ref([
  { id: 1, rank: 1, name: '川西高原3日徒步穿越', score: '4.7', count: '35043', price: '458', color: '#7ec8a0' },
  { id: 2, rank: 2, name: '秦岭太白山2日登顶', score: '4.8', count: '117', price: '1242', color: '#c8a07e' },
  { id: 3, rank: 3, name: '黄山3日2晚露营', score: '4.9', count: '89', price: '1540', color: '#7ea0c8' },
])

const flights = ref([
  { id: 1, rank: 1, from: '登山鞋', to: '防水款', tag: '户外精选', date: '秋冬款', price: '460', discount: '8折', color: '#c87e7e' },
  { id: 2, rank: 2, from: '冲锋衣', to: '三合一', tag: '户外精选', date: '防风防水', price: '480', discount: '7.5折', color: '#7ec8c8' },
  { id: 3, rank: 3, from: '登山杖', to: '碳纤维', tag: '户外精选', date: '超轻款', price: '480', discount: '8.5折', color: '#c8c87e' },
])

const guideHotels = ref([
  { id: 1, name: '专业登山鞋...', price: '918.0', color: '#4a5568' },
  { id: 2, name: '防风冲锋衣', price: '798.0', color: '#5a6578' },
  { id: 3, name: '露营帐篷套装', price: '686.0', color: '#6a7588' },
])

const routes = ref([
  {
    id: 1,
    name: '黄山环线',
    distance: '12.5km',
    duration: '6小时',
    elevation: '800m',
    score: '4.9',
    reviews: '2847',
    difficulty: 2,
    difficultyText: '中级',
    color: '#4a6741',
    region: 'near',
    tags: ['徒步', '云海', '经典'],
    favorite: true
  },
  {
    id: 2,
    name: '西湖环湖',
    distance: '8.2km',
    duration: '3小时',
    elevation: '120m',
    score: '4.8',
    reviews: '5123',
    difficulty: 1,
    difficultyText: '初级',
    color: '#5c4a3a',
    region: 'near',
    tags: ['休闲', '亲子', '城市'],
    favorite: false
  },
  {
    id: 3,
    name: '太白山穿越',
    distance: '25.6km',
    duration: '2天',
    elevation: '2200m',
    score: '4.9',
    reviews: '892',
    difficulty: 3,
    difficultyText: '高级',
    color: '#3a4a5c',
    region: 'nation',
    tags: ['穿越', '露营', '硬核'],
    favorite: false
  },
  {
    id: 4,
    name: '贡嘎西南坡',
    distance: '32km',
    duration: '3天',
    elevation: '3200m',
    score: '4.9',
    reviews: '654',
    difficulty: 3,
    difficultyText: '高级',
    color: '#6b4a5c',
    region: 'nation',
    tags: ['雪山', '摄影', '多日'],
    favorite: false
  },
  {
    id: 5,
    name: '莫干山竹海小环',
    distance: '9.8km',
    duration: '4小时',
    elevation: '450m',
    score: '4.7',
    reviews: '1806',
    difficulty: 1,
    difficultyText: '初级',
    color: '#5a7a4a',
    region: 'near',
    tags: ['竹海', '避暑', '轻徒步'],
    favorite: false
  },
  {
    id: 6,
    name: '武功山反穿',
    distance: '18.3km',
    duration: '1天',
    elevation: '1500m',
    score: '4.8',
    reviews: '3321',
    difficulty: 2,
    difficultyText: '中级',
    color: '#4a5c6b',
    region: 'nation',
    tags: ['草甸', '日出', '露营'],
    favorite: true
  },
])

const routeTabs = [
  { key: 'near', label: '周边' },
  { key: 'nation', label: '全国' },
  { key: 'fav', label: '收藏' },
]
const activeRouteTab = ref('near')
const filteredRoutes = computed(() => {
  if (activeRouteTab.value === 'near') return routes.value.filter(r => r.region === 'near')
  if (activeRouteTab.value === 'nation') return routes.value.filter(r => r.region === 'nation')
  return routes.value.filter(r => r.favorite)
})

/* ===== 导航工具界面状态 ===== */
const navMode = ref('safe')
const navForm = reactive({
  start: '当前位置',
  destination: '',
  routeType: '徒步路线',
  difficulty: '不限',
  duration: '不限',
})

const plannedRoute = ref(null)
function swapPoints() {
  ;[navForm.start, navForm.destination] = [navForm.destination, navForm.start]
}
function startNavigation() {
  const dest = navForm.destination.trim()
  if (!dest) return
  const seed = dest.length + navForm.routeType.length
  const km = (5 + (seed % 20) + (navForm.duration === '多日穿越' ? 20 : 0))
  const hours = Math.max(1, Math.round(km / (navMode.value === 'fast' ? 5.5 : 4)))
  const typeClimb = navForm.routeType === '骑行路线' ? 0.3 : navForm.routeType === '自驾路线' ? 0.5 : 1
  const climb = Math.round(km * 45 * typeClimb)
  plannedRoute.value = {
    distance: km.toFixed(1) + 'km',
    duration: hours >= 24 ? Math.round(hours / 24 * 10) / 10 + '天' : hours + '小时',
    climb: climb + 'm',
    calories: Math.round(km * 55),
    level: climb > 1000 ? '高级' : climb > 400 ? '中级' : '初级',
    waypoints: [navForm.start || '当前位置', '观景台', '补给点', dest],
  }
}

const mapLayers = [
  { key: 'standard', label: '标准' },
  { key: 'satellite', label: '卫星' },
  { key: 'terrain', label: '地形' },
]
const mapLayer = ref('standard')
const mapZoom = ref(12)
const scaleText = computed(() => {
  const meters = Math.round(2000 / Math.pow(2, mapZoom.value - 10))
  return meters >= 1000 ? (meters / 1000) + 'km' : meters + 'm'
})
const mockCoord = computed(() => {
  const offset = (18 - mapZoom.value) * 0.002
  return `${(102.9 + offset).toFixed(4)}°E, ${(30.6 + offset).toFixed(4)}°N`
})
const mockAltitude = computed(() => 1800 + (18 - mapZoom.value) * 120)

const mapControls = [
  { key: 'mark', icon: '📍', label: '标记' },
  { key: 'measure', icon: '📏', label: '测距' },
  { key: 'reset', icon: '🔄', label: '重置' },
  { key: 'offline', icon: '💾', label: '离线' },
]
const activeMapTool = ref('')
function toggleMapTool(key) {
  if (key === 'reset') {
    mapZoom.value = 12
    mapLayer.value = 'standard'
    activeMapTool.value = ''
    plannedRoute.value = null
    return
  }
  activeMapTool.value = activeMapTool.value === key ? '' : key
}

function goRoute(route) {
  navForm.destination = route.name
  navForm.routeType = '徒步路线'
  plannedRoute.value = null
  startNavigation()
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

function useTool(tool) {
  if (tool.name === '智能导航') {
    currentView.value = 'navigation'
  }
  activeMapTool.value = ''
  tool.disabled = false
}

const tools = ref([
  { id: 1, icon: '🧭', name: '智能导航', description: 'AI智能路线规划' },
  { id: 2, icon: '🗺️', name: '离线地图', description: '无网络也能导航' },
  { id: 3, icon: '📏', name: '距离测量', description: '精准测量距离' },
  { id: 4, icon: '⛰️', name: '海拔查询', description: '实时海拔数据' },
  { id: 5, icon: '🌤️', name: '天气查询', description: '户外天气预报' },
  { id: 6, icon: '⌚', name: '轨迹记录', description: '记录你的足迹' },
  { id: 7, icon: '💧', name: '水源标记', description: '共享补水点位' },
  { id: 8, icon: '🏕️', name: '营地推荐', description: '附近营地一键查' },
  { id: 9, icon: '🆘', name: '紧急求助', description: '一键SOS求助', disabled: true },
])
</script>

<style scoped>
.ctrip-layout {
  min-height: 100vh;
  background: #f0f2f5;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
}

/* 顶部导航栏 */
.top-nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #fff;
  padding: 10px 24px;
  border-bottom: 1px solid #e8e8e8;
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav-left {
  display: flex;
  align-items: center;
  gap: 24px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 6px;
}

.logo-icon {
  font-size: 28px;
}

.logo-text {
  font-size: 22px;
  font-weight: bold;
  color: #2577e3;
}

.search-bar {
  display: flex;
  border: 2px solid #2577e3;
  border-radius: 4px;
  overflow: hidden;
}

.search-bar input {
  width: 320px;
  padding: 8px 14px;
  border: none;
  outline: none;
  font-size: 14px;
}

.search-btn {
  background: #2577e3;
  color: #fff;
  border: none;
  padding: 8px 16px;
  cursor: pointer;
  font-size: 16px;
}

.nav-right {
  display: flex;
  align-items: center;
  gap: 16px;
  font-size: 14px;
}

.nav-link {
  text-decoration: none;
  color: #333;
}

.nav-link:hover {
  color: #2577e3;
}

.nav-icons {
  font-size: 18px;
  letter-spacing: 4px;
}

/* 主体布局 */
.main-body {
  display: flex;
  max-width: 1400px;
  margin: 0 auto;
  padding: 16px 0;
  gap: 0;
}

/* 左侧菜单 */
.sidebar {
  width: 180px;
  flex-shrink: 0;
  background: #fff;
  border-radius: 8px;
  padding: 8px 0;
  height: fit-content;
  position: sticky;
  top: 70px;
}

.sidebar-nav {
  display: flex;
  flex-direction: column;
}

.nav-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 20px;
  text-decoration: none;
  color: #333;
  font-size: 14px;
  transition: all 0.2s;
  position: relative;
  cursor: pointer;
}

.nav-item:hover {
  background: #e8f0fe;
  color: #1a5bc7;
}

.nav-item.active {
  background: #1a65c7;
  color: #fff;
  border-radius: 0 20px 20px 0;
  margin-right: 8px;
  font-weight: 500;
}

.nav-item.active:hover {
  background: #1557b0;
}

.nav-icon {
  font-size: 16px;
}

.badge-new {
  position: absolute;
  right: 12px;
  background: #ff6b35;
  color: #fff;
  font-size: 10px;
  padding: 1px 6px;
  border-radius: 8px;
}

.sidebar-divider {
  height: 1px;
  background: #eee;
  margin: 6px 16px;
}

/* 主内容区 */
.content {
  flex: 1;
  padding: 0 16px;
  min-width: 0;
}

/* 酒店预订表单 */
.hotel-booking {
  background: linear-gradient(135deg, #e8f4fd 0%, #d6eaf8 100%);
  border-radius: 12px;
  padding: 24px;
  margin-bottom: 16px;
}

.booking-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.booking-header h2 {
  font-size: 22px;
  color: #1a3a5c;
}

.booking-tags {
  display: flex;
  gap: 8px;
}

.tag安心订 {
  background: #2577e3;
  color: #fff;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 13px;
}

.tag放心住 {
  background: #fff;
  color: #2577e3;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 13px;
  border: 1px solid #2577e3;
}

.booking-form {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.form-row {
  display: flex;
  gap: 12px;
  align-items: flex-end;
}

.form-group {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.form-group label {
  font-size: 12px;
  color: #666;
}

.form-group input,
.form-group select {
  padding: 10px 12px;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 14px;
  outline: none;
  background: #fff;
}

.form-group input:focus,
.form-group select:focus {
  border-color: #2577e3;
}

.date-group .date-input {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 12px;
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 14px;
}

.date-input .nights {
  color: #999;
  font-size: 13px;
}

.keyword-group input {
  flex: 1;
}

.search-hotel-btn {
  background: #2577e3;
  color: #fff;
  border: none;
  padding: 10px 32px;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
  white-space: nowrap;
  height: 42px;
}

.search-hotel-btn:hover {
  background: #1a65c7;
}

/* 广告横幅 */
.promo-banner {
  background: linear-gradient(90deg, #ff6b35 0%, #f7931e 100%);
  border-radius: 12px;
  padding: 16px 24px;
  margin-bottom: 16px;
  display: flex;
  align-items: center;
}

.promo-content {
  display: flex;
  align-items: center;
  gap: 16px;
  color: #fff;
}

.promo-tag {
  background: rgba(255,255,255,0.2);
  padding: 4px 10px;
  border-radius: 4px;
  font-size: 12px;
  white-space: nowrap;
}

.promo-text h3 {
  font-size: 18px;
  margin-bottom: 4px;
}

.promo-text p {
  font-size: 14px;
  opacity: 0.9;
}

/* 快捷链接 */
.quick-links {
  display: flex;
  gap: 16px;
  margin-bottom: 16px;
}

.quick-link-item {
  flex: 1;
  display: flex;
  align-items: center;
  gap: 12px;
  background: #fff;
  padding: 16px 20px;
  border-radius: 10px;
  cursor: pointer;
  transition: box-shadow 0.2s;
}

.quick-link-item:hover {
  box-shadow: 0 2px 12px rgba(0,0,0,0.08);
}

.ql-icon {
  font-size: 28px;
}

.ql-text {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.ql-text strong {
  font-size: 16px;
  color: #333;
}

.ql-text span {
  font-size: 13px;
  color: #999;
}

/* 酒店推荐 */
.hotel-recommend {
  margin-bottom: 24px;
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}

.section-header h3 {
  font-size: 20px;
  color: #333;
}

.section-header h3 .highlight {
  color: #ff6b35;
}

.city-tabs {
  display: flex;
  gap: 8px;
}

.city-tab {
  padding: 6px 16px;
  border: 1px solid #ddd;
  border-radius: 16px;
  background: #fff;
  cursor: pointer;
  font-size: 13px;
  color: #666;
  transition: all 0.2s;
}

.city-tab.active {
  border-color: #2577e3;
  color: #2577e3;
  background: #f0f7ff;
}

.city-tab:hover {
  border-color: #2577e3;
  color: #2577e3;
}

.hotel-cards {
  display: flex;
  gap: 16px;
}

.hotel-card {
  flex: 1;
  background: #fff;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  transition: transform 0.2s, box-shadow 0.2s;
  cursor: pointer;
}

.hotel-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}

.hotel-img {
  height: 160px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.hotel-img-text {
  color: #fff;
  font-size: 18px;
  font-weight: bold;
  text-shadow: 0 1px 3px rgba(0,0,0,0.3);
}

.ad-tag {
  position: absolute;
  top: 8px;
  right: 8px;
  background: rgba(0,0,0,0.5);
  color: #fff;
  font-size: 11px;
  padding: 2px 8px;
  border-radius: 3px;
}

.hotel-info {
  padding: 12px;
}

.hotel-info h4 {
  font-size: 14px;
  color: #333;
  margin-bottom: 6px;
  line-height: 1.4;
}

.hotel-rating {
  display: flex;
  align-items: center;
  gap: 6px;
  margin-bottom: 8px;
}

.rating-score {
  background: #2577e3;
  color: #fff;
  padding: 1px 6px;
  border-radius: 3px;
  font-size: 12px;
  font-weight: bold;
}

.rating-label {
  color: #2577e3;
  font-size: 12px;
  font-weight: bold;
}

.rating-review {
  color: #999;
  font-size: 12px;
}

.hotel-price {
  text-align: right;
}

.original-price {
  color: #ccc;
  text-decoration: line-through;
  font-size: 13px;
  margin-right: 6px;
}

.current-price {
  color: #ff6b35;
  font-size: 20px;
  font-weight: bold;
}

/* 当季热推 */
.seasonal-recommend {
  margin-bottom: 24px;
}

.departure-select {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 14px;
  color: #666;
}

.departure-select select {
  padding: 4px 12px;
  border: 1px solid #ddd;
  border-radius: 4px;
  outline: none;
}

.seasonal-grid {
  display: flex;
  gap: 16px;
}

.seasonal-block {
  flex: 1;
  background: #fff;
  border-radius: 10px;
  padding: 16px;
}

.block-header {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 12px;
}

.block-icon {
  font-size: 20px;
}

.block-header h4 {
  font-size: 15px;
  color: #333;
}

.tour-list,
.flight-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.tour-item,
.flight-item {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 8px 0;
  border-bottom: 1px solid #f5f5f5;
}

.tour-rank,
.flight-rank {
  width: 20px;
  height: 20px;
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  flex-shrink: 0;
}

.rank-1 { background: #ff4444; }
.rank-2 { background: #ff8c00; }
.rank-3 { background: #ffcc00; color: #333; }

.tour-img,
.flight-img {
  width: 60px;
  height: 45px;
  border-radius: 6px;
  flex-shrink: 0;
}

.tour-info,
.flight-info {
  flex: 1;
  min-width: 0;
}

.tour-name {
  font-size: 13px;
  color: #333;
  margin-bottom: 4px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.tour-meta {
  display: flex;
  gap: 8px;
  font-size: 12px;
  color: #999;
}

.tour-score {
  color: #2577e3;
}

.tour-price {
  color: #ff6b35;
  font-size: 14px;
  font-weight: bold;
  white-space: nowrap;
}

.flight-route {
  font-size: 13px;
  color: #333;
  font-weight: bold;
}

.flight-tag {
  display: inline-block;
  background: #e8f5e9;
  color: #4caf50;
  font-size: 11px;
  padding: 1px 6px;
  border-radius: 3px;
  margin-top: 2px;
}

.flight-date {
  font-size: 11px;
  color: #999;
  margin-top: 2px;
}

.flight-price-area {
  text-align: right;
  white-space: nowrap;
}

.flight-price {
  color: #ff6b35;
  font-size: 14px;
  font-weight: bold;
}

.flight-discount {
  font-size: 11px;
  color: #999;
}

/* 右侧栏 */
.right-sidebar {
  width: 260px;
  flex-shrink: 0;
  padding-left: 16px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.city-guide {
  background: linear-gradient(180deg, #1a3a5c 0%, #2c5282 100%);
  border-radius: 12px;
  padding: 16px;
  color: #fff;
  position: relative;
  overflow: hidden;
  min-height: 380px;
}

.city-guide h4 {
  font-size: 15px;
  margin-bottom: 12px;
}

.guide-carousel {
  margin-bottom: 12px;
}

.carousel-dots {
  display: flex;
  gap: 6px;
  justify-content: center;
}

.dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: rgba(255,255,255,0.4);
}

.dot.active {
  background: #fff;
  width: 20px;
  border-radius: 4px;
}

.guide-hotels {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.guide-hotel-item {
  display: flex;
  align-items: center;
  gap: 10px;
  background: rgba(255,255,255,0.15);
  padding: 8px 10px;
  border-radius: 8px;
}

.guide-hotel-img {
  width: 50px;
  height: 40px;
  border-radius: 6px;
  flex-shrink: 0;
}

.guide-hotel-info {
  display: flex;
  flex-direction: column;
  gap: 2px;
  font-size: 13px;
}

.guide-hotel-price {
  color: #ffd700;
  font-size: 12px;
}

.ranking-banner {
  background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
  border-radius: 12px;
  padding: 20px;
  color: #fff;
  cursor: pointer;
}

.ranking-content h4 {
  font-size: 18px;
  margin-bottom: 4px;
}

.ranking-content p {
  font-size: 13px;
  opacity: 0.8;
}

.business-banner {
  background: linear-gradient(135deg, #2577e3 0%, #1a5fc7 100%);
  border-radius: 12px;
  padding: 20px;
  color: #fff;
  cursor: pointer;
}

.business-content h4 {
  font-size: 18px;
  margin-bottom: 4px;
}

.business-content p {
  font-size: 12px;
  opacity: 0.85;
}

/* 导航搜索模块 */
.navigation-search {
  background: linear-gradient(135deg, #e8f4fd 0%, #d6eaf8 100%);
  border-radius: 12px;
  padding: 24px;
  margin-bottom: 16px;
}

.search-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.search-header h2 {
  font-size: 22px;
  color: #1a3a5c;
}

.search-tags {
  display: flex;
  gap: 8px;
}

.tag-safe {
  background: #2577e3;
  color: #fff;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 13px;
}

.tag-fast {
  background: #fff;
  color: #2577e3;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 13px;
  border: 1px solid #2577e3;
}

.search-form {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.form-row {
  display: flex;
  gap: 12px;
  align-items: flex-end;
}

.form-group {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.form-group label {
  font-size: 12px;
  color: #666;
}

.form-group input,
.form-group select {
  padding: 10px 12px;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 14px;
  outline: none;
  background: #fff;
}

.form-group input:focus,
.form-group select:focus {
  border-color: #2577e3;
}

.search-route-btn {
  background: #2577e3;
  color: #fff;
  border: none;
  padding: 10px 32px;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
  white-space: nowrap;
  height: 42px;
}

.search-route-btn:hover {
  background: #1a65c7;
}

/* 地图容器 */
.map-container {
  background: #fff;
  border-radius: 12px;
  padding: 20px;
  margin-bottom: 16px;
  position: relative;
}

.map-controls {
  display: flex;
  gap: 12px;
  margin-top: 16px;
}

.control-btn {
  padding: 8px 16px;
  border: 1px solid #ddd;
  border-radius: 6px;
  background: #fff;
  cursor: pointer;
  font-size: 14px;
  transition: all 0.2s;
}

.control-btn:hover {
  border-color: #2577e3;
  color: #2577e3;
}

/* 热门路线 */
.popular-routes {
  margin-bottom: 24px;
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}

.section-header h3 {
  font-size: 20px;
  color: #333;
}

.section-header h3 .highlight {
  color: #ff6b35;
}

.route-tabs {
  display: flex;
  gap: 8px;
}

.route-tab {
  padding: 6px 16px;
  border: 1px solid #ddd;
  border-radius: 16px;
  background: #fff;
  cursor: pointer;
  font-size: 13px;
  color: #666;
  transition: all 0.2s;
}

.route-tab.active {
  border-color: #2577e3;
  color: #2577e3;
  background: #f0f7ff;
}

.route-cards {
  display: flex;
  gap: 16px;
}

.route-card {
  flex: 1;
  background: #fff;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  transition: transform 0.2s, box-shadow 0.2s;
  cursor: pointer;
}

.route-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}

.route-img {
  height: 140px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.route-img-text {
  color: #fff;
  font-size: 16px;
  font-weight: bold;
  text-shadow: 0 1px 3px rgba(0,0,0,0.3);
}

.difficulty-badge {
  position: absolute;
  top: 8px;
  right: 8px;
  padding: 4px 10px;
  border-radius: 12px;
  font-size: 11px;
  font-weight: bold;
}

.level-1 {
  background: #4caf50;
  color: #fff;
}

.level-2 {
  background: #ff9800;
  color: #fff;
}

.level-3 {
  background: #f44336;
  color: #fff;
}

.route-info {
  padding: 12px;
}

.route-info h4 {
  font-size: 14px;
  color: #333;
  margin-bottom: 8px;
}

.route-stats {
  display: flex;
  gap: 12px;
  margin-bottom: 8px;
  font-size: 12px;
  color: #666;
}

.stat-item {
  white-space: nowrap;
}

.route-rating {
  display: flex;
  align-items: center;
  gap: 8px;
}

.rating-score {
  background: #2577e3;
  color: #fff;
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 13px;
  font-weight: bold;
}

.rating-count {
  color: #999;
  font-size: 12px;
}

/* 工具网格 */
.tool-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  margin-bottom: 24px;
}

.tool-card {
  background: #fff;
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  transition: transform 0.2s, box-shadow 0.2s;
  cursor: pointer;
}

.tool-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}

.tool-card-icon {
  font-size: 40px;
  margin-bottom: 12px;
}

.tool-card h4 {
  font-size: 16px;
  color: #333;
  margin-bottom: 8px;
}

.tool-card p {
  font-size: 13px;
  color: #999;
  margin-bottom: 12px;
}

.tool-use-btn {
  padding: 8px 20px;
  border: 1px solid #2577e3;
  border-radius: 6px;
  background: #fff;
  color: #2577e3;
  cursor: pointer;
  font-size: 13px;
  transition: all 0.2s;
}

.tool-use-btn:hover {
  background: #2577e3;
  color: #fff;
}

/* ===== 导航工具界面完善 ===== */
.tag-safe,
.tag-fast {
  cursor: pointer;
  opacity: 0.75;
  transition: all 0.2s;
}

.tag-safe.active,
.tag-fast.active {
  opacity: 1;
  box-shadow: 0 2px 6px rgba(37, 119, 227, 0.3);
}

.point-input {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 0 10px;
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 6px;
  transition: border-color 0.2s;
}

.point-input:focus-within {
  border-color: #2577e3;
}

.point-input input {
  flex: 1;
  border: none !important;
  padding-left: 0 !important;
  min-width: 0;
}

.point-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  flex-shrink: 0;
}

.point-dot.start {
  background: #4caf50;
}

.point-dot.end {
  background: #f44336;
}

.swap-btn {
  border: none;
  background: #f0f7ff;
  color: #2577e3;
  width: 26px;
  height: 26px;
  border-radius: 50%;
  cursor: pointer;
  font-size: 14px;
  transition: all 0.2s;
}

.swap-btn:hover {
  background: #2577e3;
  color: #fff;
}

/* 规划结果 */
.route-result {
  margin-top: 16px;
  background: #fff;
  border-radius: 10px;
  padding: 16px 20px;
  border-left: 4px solid #2577e3;
}

.result-summary {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
}

.result-item {
  flex: 1;
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.result-value {
  font-size: 18px;
  font-weight: bold;
  color: #2577e3;
}

.result-value.level-text {
  color: #ff9800;
}

.result-label {
  font-size: 12px;
  color: #999;
}

.result-waypoints {
  font-size: 13px;
  color: #666;
  padding-top: 10px;
  border-top: 1px dashed #e8e8e8;
}

.wp-label {
  color: #333;
  font-weight: 500;
}

.wp-item em {
  color: #2577e3;
  font-style: normal;
  font-weight: bold;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s, transform 0.25s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-6px);
}

/* 地图工具栏与画布 */
.map-toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.layer-tabs {
  display: flex;
  gap: 6px;
}

.layer-tab {
  padding: 5px 14px;
  border: 1px solid #ddd;
  border-radius: 14px;
  background: #fff;
  cursor: pointer;
  font-size: 13px;
  color: #666;
  transition: all 0.2s;
}

.layer-tab.active {
  background: #2577e3;
  border-color: #2577e3;
  color: #fff;
}

.map-coord {
  font-size: 12px;
  color: #888;
  font-family: Consolas, monospace;
}

.map-canvas {
  height: 400px;
  border-radius: 8px;
  position: relative;
  overflow: hidden;
  transition: background 0.3s;
}

.map-canvas.layer-standard {
  background: linear-gradient(135deg, #e8f4e0 0%, #d0e8f0 60%, #c8dcf0 100%);
}

.map-canvas.layer-satellite {
  background: linear-gradient(135deg, #3d5233 0%, #4a5d3a 50%, #2c3e26 100%);
}

.map-canvas.layer-terrain {
  background: linear-gradient(135deg, #f0e4d0 0%, #d8c8a8 50%, #c8b898 100%);
}

.map-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.25) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.25) 1px, transparent 1px);
  background-size: 60px 60px;
  pointer-events: none;
}

.map-route {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.map-canvas.layer-satellite .map-route path {
  stroke: #ffd700;
}

.map-marker {
  position: absolute;
  width: 26px;
  height: 26px;
  border-radius: 50% 50% 50% 0;
  transform: rotate(-45deg);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-size: 12px;
  font-weight: bold;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
}

.map-marker > * {
  transform: rotate(45deg);
}

.marker-start {
  background: #4caf50;
}

.marker-end {
  background: #f44336;
}

.zoom-controls {
  position: absolute;
  right: 14px;
  top: 14px;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}

.zoom-controls button {
  width: 34px;
  height: 34px;
  border: none;
  background: transparent;
  font-size: 18px;
  cursor: pointer;
  color: #333;
}

.zoom-controls button:hover {
  background: #f0f7ff;
  color: #2577e3;
}

.zoom-level {
  font-size: 11px;
  color: #999;
  border-top: 1px solid #eee;
  border-bottom: 1px solid #eee;
  width: 100%;
  text-align: center;
  padding: 2px 0;
}

.locate-btn {
  position: absolute;
  right: 14px;
  bottom: 40px;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background: #fff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  cursor: pointer;
  font-size: 18px;
  color: #2577e3;
}

.locate-btn:hover {
  background: #f0f7ff;
}

.map-scale {
  position: absolute;
  left: 14px;
  bottom: 14px;
  background: rgba(255, 255, 255, 0.85);
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 11px;
  color: #555;
}

/* 地图控制按钮激活态 */
.control-btn.active {
  background: #2577e3;
  border-color: #2577e3;
  color: #fff;
}

/* 热门路线卡片增强 */
.route-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 8px;
}

.route-tag {
  background: #f0f5ff;
  color: #2577e3;
  font-size: 11px;
  padding: 2px 8px;
  border-radius: 10px;
}

.route-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.fav-btn {
  position: absolute;
  top: 8px;
  left: 8px;
  width: 28px;
  height: 28px;
  border: none;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.85);
  font-size: 15px;
  cursor: pointer;
  color: #999;
  transition: all 0.2s;
}

.fav-btn.faved {
  color: #ffb400;
}

.fav-btn:hover {
  transform: scale(1.1);
}

.route-nav-btn {
  padding: 6px 16px;
  border: 1px solid #2577e3;
  border-radius: 14px;
  background: #2577e3;
  color: #fff;
  font-size: 12px;
  cursor: pointer;
  transition: all 0.2s;
}

.route-nav-btn:hover {
  background: #1a65c7;
  border-color: #1a65c7;
}

.route-empty {
  flex: 1;
  background: #fff;
  border-radius: 10px;
  padding: 40px;
  text-align: center;
  color: #999;
  font-size: 14px;
}

/* 工具集区块 */
.tools-section {
  margin-bottom: 24px;
}

.tools-count {
  font-size: 13px;
  color: #999;
}

.tool-card.disabled {
  opacity: 0.6;
}

.tool-use-btn:disabled {
  border-color: #ddd;
  color: #bbb;
  cursor: not-allowed;
}

.tool-use-btn:disabled:hover {
  background: #fff;
}
</style>
