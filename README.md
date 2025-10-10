# UH-courses

This repository contains course data from various University of Hawaii (UH) campuses and the Pacific Center for Advanced Technology Training (PCATT). The data is available in both JSON and CSV formats.

## Data Structure

### File Organization

- **`json_format/`** - Contains all course data in JSON format
- **Root directory** - Contains all course data in CSV format

### Available Datasets

#### UH Campus Course Data (JSON and CSV)
- `hawaiicc_courses` - Hawaii Community College
- `hilo_courses` - University of Hawaii at Hilo
- `honolulucc_courses` - Honolulu Community College
- `kapiolani_courses` - Kapiolani Community College
- `kauai_courses` - Kauai Community College
- `leeward_courses` - Leeward Community College
- `manoa_courses` - University of Hawaii at Manoa
- `maui_courses` - University of Hawaii Maui College
- `west_oahu_courses` - University of Hawaii West Oahu
- `windward_courses` - Windward Community College

#### PCATT Course Data (JSON and CSV)
- `pcatt_courses` - Pacific Center for Advanced Technology Training

## Data Fields

### Standard UH Campus Courses (8 fields)

| Field | Type | Description |
|-------|------|-------------|
| `course_prefix` | String | Course subject prefix (e.g., "Acc", "Eng", "Math") |
| `course_number` | String | Course number (e.g., "124", "100", "201") |
| `course_title` | String | Full course title |
| `course_desc` | String | Detailed course description |
| `num_units` | String | Number of credit units (e.g., "3", "4") |
| `dept_name` | String | Department name offering the course |
| `inst_ipeds` | Integer | IPEDS institution identifier |
| `metadata` | String | Additional course information (prerequisites, hours, etc.) |

### PCATT Courses (7 fields)

PCATT courses have the same structure as UH campus courses but **exclude** the `num_units` field:

| Field | Type | Description |
|-------|------|-------------|
| `course_prefix` | String | Course subject prefix (e.g., "Com") |
| `course_number` | String | Course number (e.g., "2158", "2162") |
| `course_title` | String | Full course title |
| `course_desc` | String | Detailed course description |
| `dept_name` | String | Always "Pacific Center for Advanced Technology Training" |
| `inst_ipeds` | Integer | IPEDS institution identifier (383190) |
| `metadata` | String | Additional course information (prerequisites, hours, etc.) |

## Data Formats

### JSON Format
- Files are located in the `json_format/` directory
- Each file contains an array of course objects
- UTF-8 encoded with proper JSON formatting
- Example structure:
```json
[
  {
    "course_prefix": "Acc",
    "course_number": "124",
    "course_title": "Principles of Accounting I",
    "course_desc": "Accounting theory and methods...",
    "num_units": "3",
    "dept_name": "Accounting",
    "inst_ipeds": 383190,
    "metadata": "Pre: 'C' or better in Eng 21..."
  }
]
```

### CSV Format
- Files are located in the root directory
- First row contains column headers
- UTF-8 encoded with comma-separated values
- Text fields containing commas are properly quoted
- Example structure:
```csv
course_prefix,course_number,course_title,course_desc,num_units,dept_name,inst_ipeds,metadata
Acc,124,Principles of Accounting I,Accounting theory and methods...,3,Accounting,383190,"Pre: 'C' or better in Eng 21..."
```

## Institution IPEDS Codes

| Institution | IPEDS Code |
|-------------|------------|
| Hawaii Community College | 383190 |
| University of Hawaii at Hilo | 141990 |
| Honolulu Community College | 141680 |
| Kapiolani Community College | 141796 |
| Kauai Community College | 141802 |
| Leeward Community College | 141811 |
| University of Hawaii at Manoa | 141574 |
| University of Hawaii Maui College | 141839 |
| University of Hawaii West Oahu | 141981 |
| Windward Community College | 141990 |
| Pacific Center for Advanced Technology Training | 383190 |

## Usage Notes

- All course data is current as of the last update
- Course descriptions and metadata may contain special characters and formatting
- Some courses may have empty or minimal metadata fields
- PCATT courses focus on technology training and certification programs
- UH campus courses represent traditional academic offerings

## File Sizes

The dataset includes thousands of courses across all institutions, with the largest files being:
- `manoa_courses` (University of Hawaii at Manoa) - largest dataset
- `kapiolani_courses` (Kapiolani Community College)
- `maui_courses` (University of Hawaii Maui College)

## Data Quality

- All JSON files have been validated for proper structure
- Property consistency has been verified across all files
- CSV files are properly formatted with appropriate escaping
- Department names have been standardized (PCATT courses use full department name)