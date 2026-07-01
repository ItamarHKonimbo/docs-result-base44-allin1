## Product

### Schema

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `itemId` | string | Yes | Product ID from supplier |
| `category` | string |  | Main category in Hebrew |
| `subCategory` | string |  | Subcategory in Hebrew |
| `name` | string | Yes | Product name in Hebrew |
| `itemModel` | string |  | Model number |
| `manufactModel` | string |  | Manufacturer's model number |
| `manufactName` | string |  | Manufacturer name |
| `manufacturerURL` | string |  | Manufacturer or product page URL |
| `costPrice` | number |  | Supplier cost price |
| `regularPrice` | number |  | Calculated retail price |
| `inventory` | number |  | Stock status: 100 (in stock) or -100 (out of stock) |
| `paymentsNoCredit` | number |  |  |
| `deliveryTime` | number |  |  |
| `maxPayments` | number |  |  |
| `warranty` | number |  | Warranty duration in months |
| `warrantyText` | string |  | Warranty description text (e.g. שנה אחת אחריות) |
| `supplierName` | `מור לוי`, `אול אין וואן`, `קומפיוטר סי דאטה`, `טונוס`, `מתקינט`, `מפעיל`, `טכנורצף` |  | Supplier name |
| `images` | string |  | Image URLs separated by semicolon |
| `מפרט` | string |  | HTML specification table |
| `סטטוס מוצר` | boolean |  | האם המוצר פעיל |
| `updated_at` | string |  | Timestamp of last price/inventory update |
| `friendlyurl` | string |  | Friendly URL slug (same as itemId) |
| `name_parsed` | boolean |  | Whether the product name has been parsed |
| `שם מוצר מנותח` | string |  | Parsed product name |
| `name_committed` | boolean |  | Whether the parsed name has been committed |
| `last_price` | string |  | Last known price (text) |
| `last_price_date` | string |  | Date of last known price |
| `on_the_way_inventory` | `true`, `false`, `null` |  | Is the product on the way / incoming inventory |
| `GMF_יצרן` | string |  |  |
| `GMF_סוג זיכרון ראם` | string |  |  |
| `GMF_ערכת שבבים` | string |  |  |
| `GMF_תושבת מעבד` | string |  |  |
| `GMF_מהירות זיכרון ראם` | string |  |  |
| `GMF_דור אחסון` | string |  |  |
| `GMF_נפח זיכרון גרפי` | string |  |  |
| `GMF_הספק` | string |  |  |
| `GMF_ספק` | string |  |  |
| `GMF_תצורה` | string |  |  |
| `GMF_סוג פאנל` | string |  |  |
| `GMF_שטוח / קעור` | string |  |  |
| `GMF_דור WIFI` | string |  |  |
| `GMF_קצב העברת נתונים` | string |  |  |
| `GMF_כמות פורטים` | string |  |  |
| `GMF_סלולרי (LTE)` | string |  |  |
| `GMF_סוג חיבור` | string |  |  |
| `GMF_כולל / לא כולל מסך מגע` | string |  |  |
| `GMF_משך וסוג אחריות` | string |  |  |
| `GMF_גודל` | string |  |  |
| `GMF_גודל מסך` | string |  |  |
| `GMF_נפח זיכרון ראם` | string |  |  |
| `GMF_נפח אחסון` | string |  |  |
| `GMF_מעבד` | string |  |  |
| `GMF_מעבד גרפי` | string |  |  |
| `GMF_כולל / לא כולל מע' הפעלה` | string |  |  |
| `GMF_תקן` | string |  |  |
| `GMF_סוג מוצר` | string |  |  |
| `GMF_תקציב` | string |  |  |
| `id` | string |  | Unique record identifier |
| `created_date` | string |  | Record creation timestamp |
| `updated_date` | string |  | Record last update timestamp |
| `created_by_id` | string |  | ID of the user who created the record |

### Endpoints

### `GET /entities/Product`
List Product records

**Parameters:**
- `q` (query): JSON query filter, e.g. {"status":"active"}
- `limit` (query): Maximum number of records to return
- `skip` (query): Number of records to skip (pagination)
- `sort_by` (query): Field name to sort by. Prefix with '-' for descending order, e.g. -created_date

```javascript
const records = await base44.entities.Product.list();
```

### `POST /entities/Product`
Create a Product record

```javascript
const record = await base44.entities.Product.create({
  // your data
});
```

### `DELETE /entities/Product`
Delete multiple Product records

```javascript
await base44.entities.Product.deleteMany({
  // query filter — WARNING: empty {} deletes ALL records
  itemId: "Example itemId"
});
```

### `POST /entities/Product/bulk`
Bulk create Product records

```javascript
const records = await base44.entities.Product.bulkCreate([
  { /* record 1 */ },
  { /* record 2 */ },
]);
```

### `PUT /entities/Product/bulk`
Bulk update Product records

```javascript
// bulk-update is not available via SDK — use the REST API
```

### `PATCH /entities/Product/update-many`
Update many Product records by query

```javascript
// update-many is not available via SDK — use the REST API
```

### `GET /entities/Product/{Product_id}`
Get a Product record by ID

**Parameters:**
- `Product_id` (path): Record ID

```javascript
const record = await base44.entities.Product.get(recordId);
```

### `PUT /entities/Product/{Product_id}`
Update a Product record

**Parameters:**
- `Product_id` (path): Record ID

```javascript
const record = await base44.entities.Product.update(recordId, {
  // fields to update
});
```

### `DELETE /entities/Product/{Product_id}`
Delete a Product record

**Parameters:**
- `Product_id` (path): Record ID

```javascript
await base44.entities.Product.delete(recordId);
```

### `PUT /entities/Product/{Product_id}/restore`
Restore a deleted Product record

**Parameters:**
- `Product_id` (path): Record ID

```javascript
const record = await base44.entities.Product.restore(recordId);
```