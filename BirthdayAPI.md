## 🎂 **1. BirthdayAPI**

### 📘 **Overview**

The **BirthdayAPI** automates fetching, managing, and processing subscriber birthdays every week.

It collects birthday data every Monday and triggers a robot to process delivery tasks a few days before each event. A site sends birthday cards based on the subscribers' needs every year. These subscribers are so busy that they left this process of wishing thier loved ones with the list of items, needs and they go on with thier own work. THe site atomates the process using the APIs, Agentetic Robots, Delivery usinf Autonomous Vechicles. Write a BirthdayAPI which helps to gets data about that weeks' birthday people, makes a list collects details whenever Monday  begins. On a dialy basis, an Highly secured Agentetic robot gets this data from the site using an API so that it processes and send the cards either couple of days before the birthday, giving it some time to delilver. There are endpoints to reach the address of the subscribers, the data on thier likings, gifts, coupons, etc. Also write an API for the delivery Agentic AI who take cares of the delivery at the door. This will have address, route of delivery ets.

---

### 🧩 **Base URL**

<pre class="overflow-visible!" data-start="723" data-end="765"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>https:</span><span>//api.birthdayservice.com/v1</span><span>
</span></span></code></div></div></pre>

---

### 🧠 **Main Functions**

* Fetch birthdays of the week
* Retrieve subscriber details (likes, gifts, coupons, address)
* Schedule card creation and delivery
* Notify delivery robots in advance

---

### 🛠️ **Endpoints**

#### **GET /birthdays/week**

Fetch all subscribers with birthdays in the current week.

**Request Example:**

<pre class="overflow-visible!" data-start="1109" data-end="1140"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>GET /birthdays/week
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="1156" data-end="1514"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"weekStart"</span><span>:</span><span></span><span>"2025-10-13"</span><span>,</span><span>
  </span><span>"weekEnd"</span><span>:</span><span></span><span>"2025-10-19"</span><span>,</span><span>
  </span><span>"birthdays"</span><span>:</span><span></span><span>[</span><span>
    </span><span>{</span><span>
      </span><span>"subscriberId"</span><span>:</span><span></span><span>"S1001"</span><span>,</span><span>
      </span><span>"name"</span><span>:</span><span></span><span>"Ava Johnson"</span><span>,</span><span>
      </span><span>"birthday"</span><span>:</span><span></span><span>"2025-10-15"</span><span>,</span><span>
      </span><span>"daysUntilBirthday"</span><span>:</span><span></span><span>2</span><span>
    </span><span>}</span><span>,</span><span>
    </span><span>{</span><span>
      </span><span>"subscriberId"</span><span>:</span><span></span><span>"S1020"</span><span>,</span><span>
      </span><span>"name"</span><span>:</span><span></span><span>"Liam Brown"</span><span>,</span><span>
      </span><span>"birthday"</span><span>:</span><span></span><span>"2025-10-18"</span><span>,</span><span>
      </span><span>"daysUntilBirthday"</span><span>:</span><span></span><span>5</span><span>
    </span><span>}</span><span>
  </span><span>]</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

#### **GET /subscribers/**

Fetch complete subscriber details including preferences.

**Example Request:**

<pre class="overflow-visible!" data-start="1631" data-end="1665"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>GET /subscribers/S1001
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="1681" data-end="1938"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"subscriberId"</span><span>:</span><span></span><span>"S1001"</span><span>,</span><span>
  </span><span>"name"</span><span>:</span><span></span><span>"Ava Johnson"</span><span>,</span><span>
  </span><span>"birthday"</span><span>:</span><span></span><span>"2025-10-15"</span><span>,</span><span>
  </span><span>"address"</span><span>:</span><span></span><span>"42 Elm Street, Boston, MA"</span><span>,</span><span>
  </span><span>"preferences"</span><span>:</span><span></span><span>{</span><span>
    </span><span>"cardTheme"</span><span>:</span><span></span><span>"Floral"</span><span>,</span><span>
    </span><span>"giftType"</span><span>:</span><span></span><span>"Perfume"</span><span>,</span><span>
    </span><span>"couponPreference"</span><span>:</span><span></span><span>"Amazon Gift Card"</span><span>
  </span><span>}</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

#### **POST /birthdays/schedule**

Triggered every Monday — collects all birthdays of the week and schedules deliveries.

**Example Request:**

<pre class="overflow-visible!" data-start="2087" data-end="2123"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>POST /birthdays/schedule
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="2139" data-end="2254"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"message"</span><span>:</span><span></span><span>"Weekly schedule created successfully"</span><span>,</span><span>
  </span><span>"totalBirthdays"</span><span>:</span><span></span><span>48</span><span>,</span><span>
  </span><span>"deliveryQueued"</span><span>:</span><span></span><span>45</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

#### **POST /birthdays/notify**

Notify Agentic Robots to begin card processing.

**Example Request:**

<pre class="overflow-visible!" data-start="2363" data-end="2457"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>POST /birthdays/notify
{
  "robotId": "AR-9001",
  "scheduledDate": "2025-10-13"
}
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="2473" data-end="2576"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"status"</span><span>:</span><span></span><span>"success"</span><span>,</span><span>
  </span><span>"message"</span><span>:</span><span></span><span>"Robot AR-9001 notified for this week’s birthdays."</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

---

## **2. DeliveryAPI**

### **Overview**

The **DeliveryAPI** is used by the **Agentic AI delivery robots** to plan routes, deliver birthday cards, and confirm successful delivery.

---

### **Base URL**

<pre class="overflow-visible!" data-start="2799" data-end="2841"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>https:</span><span>//api.deliveryservice.com/v1</span><span>
</span></span></code></div></div></pre>

---

### 🛠️ **Endpoints**

#### **GET /delivery/routes**

Get optimized delivery route for today’s deliveries.

**Example Request:**

<pre class="overflow-visible!" data-start="2976" data-end="3024"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>GET /delivery/routes?date=2025-10-14
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="3040" data-end="3461"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"date"</span><span>:</span><span></span><span>"2025-10-14"</span><span>,</span><span>
  </span><span>"route"</span><span>:</span><span></span><span>[</span><span>
    </span><span>{</span><span>
      </span><span>"deliveryId"</span><span>:</span><span></span><span>"D-2001"</span><span>,</span><span>
      </span><span>"subscriberId"</span><span>:</span><span></span><span>"S1001"</span><span>,</span><span>
      </span><span>"address"</span><span>:</span><span></span><span>"42 Elm Street, Boston, MA"</span><span>,</span><span>
      </span><span>"ETA"</span><span>:</span><span></span><span>"09:30 AM"</span><span>,</span><span>
      </span><span>"packageType"</span><span>:</span><span></span><span>"Birthday Card"</span><span>
    </span><span>}</span><span>,</span><span>
    </span><span>{</span><span>
      </span><span>"deliveryId"</span><span>:</span><span></span><span>"D-2002"</span><span>,</span><span>
      </span><span>"subscriberId"</span><span>:</span><span></span><span>"S1020"</span><span>,</span><span>
      </span><span>"address"</span><span>:</span><span></span><span>"89 Maple Avenue, New York, NY"</span><span>,</span><span>
      </span><span>"ETA"</span><span>:</span><span></span><span>"12:45 PM"</span><span>,</span><span>
      </span><span>"packageType"</span><span>:</span><span></span><span>"Card + Gift"</span><span>
    </span><span>}</span><span>
  </span><span>]</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

#### **POST /delivery/confirm**

Delivery robot updates the status after successful drop-off.

**Request:**

<pre class="overflow-visible!" data-start="3575" data-end="3741"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>POST /delivery/confirm
{
  "deliveryId": "D-2001",
  "status": "Delivered",
  "timestamp": "2025-10-14T09:32:00Z",
  "recipientSignature": "Ava Johnson"
}
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="3757" data-end="3837"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"status"</span><span>:</span><span></span><span>"success"</span><span>,</span><span>
  </span><span>"message"</span><span>:</span><span></span><span>"Delivery D-2001 confirmed."</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

#### **GET /delivery/status/**

Fetch status of a specific delivery.

**Example Request:**

<pre class="overflow-visible!" data-start="3938" data-end="3977"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-http"><span>GET /delivery/status/D-2001
</span></code></div></div></pre>

**Response:**

<pre class="overflow-visible!" data-start="3993" data-end="4097"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-json"><span><span>{</span><span>
  </span><span>"deliveryId"</span><span>:</span><span></span><span>"D-2001"</span><span>,</span><span>
  </span><span>"status"</span><span>:</span><span></span><span>"Delivered"</span><span>,</span><span>
  </span><span>"timestamp"</span><span>:</span><span></span><span>"2025-10-14T09:32:00Z"</span><span>
</span><span>}</span><span>
</span></span></code></div></div></pre>

---

### **Security**

All API calls are secured using:

* API Keys for authentication
* Encrypted payloads for personal data
* HTTPS-only transport

---

## **Workflow Summary**

| Day               | Process                          | Responsible API                       |
| ----------------- | -------------------------------- | ------------------------------------- |
| Monday            | Collect weekly birthdays         | BirthdayAPI (`/birthdays/schedule`) |
| Tuesday–Saturday | Robots process and prepare cards | BirthdayAPI + internal robot logic    |
| Delivery Day      | Send via autonomous vehicles     | DeliveryAPI                           |
| After Delivery    | Confirm completion               | DeliveryAPI (`/delivery/confirm`)   |
