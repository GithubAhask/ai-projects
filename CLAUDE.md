# AI Assistant Guidelines for AI Projects

## Overview
This document provides instructions for AI assistants working on this codebase. Follow these guidelines to maintain consistency and meet project requirements.

## Code Style Preferences

### Languages
- **Primary Languages**: Python, React (JavaScript/JSX), Java
- **Naming Convention**: camelCase for all variables and functions
- **Indentation**: Use tabs (not spaces)
- **Comments**: 
	- Provide detailed comments explaining what each section does
	- Write comments that are beginner-friendly
	- Label key components with descriptive names that can be referenced in simple language

### Code Readability Requirements
```python
# Example Python style:
def calculateUserScore(userData):
	"""
	Calculate the user's score based on their activity data.
	This function takes user data and returns a numerical score.
	"""
	# Step 1: Extract relevant metrics from user data
	loginCount = userData['logins']
	activityLevel = userData['activities']
	
	# Step 2: Apply scoring algorithm
	# Base score starts at 0, adds points for each login and activity
	baseScore = 0
	scoreFromLogins = loginCount * 10  # Each login worth 10 points
	scoreFromActivity = activityLevel * 5  # Each activity worth 5 points
	
	# Step 3: Calculate and return final score
	finalScore = baseScore + scoreFromLogins + scoreFromActivity
	return finalScore
```

## Framework & Library Guidelines

### Approach
- **Guidance**: Since the user is new to development, explain library choices
- **Selection**: Recommend appropriate libraries for each project with rationale
- **Documentation**: Include links to documentation and explain why each library is beneficial

### Common Recommendations
- **Python**: Start with standard library, introduce pip packages as needed
- **React**: Begin with Create React App, explain additional libraries when relevant
- **Java**: Use standard Java SDK first, introduce Maven/Gradle dependencies with explanation

## Development Practices

### Testing & Debugging
- Include debugging test snippets in all code
- Add console.log/print statements at key points for visibility
- Create simple test cases that can be run immediately

Example:
```javascript
// React component with debugging
function UserProfile({ userId }) {
	// Debug: Log when component renders
	console.log('UserProfile rendering for user:', userId);
	
	const [userData, setUserData] = useState(null);
	
	// Debug: Log data fetching
	useEffect(() => {
		console.log('Fetching data for user:', userId);
		fetchUserData(userId)
			.then(data => {
				console.log('Data received:', data);
				setUserData(data);
			})
			.catch(error => {
				console.error('Error fetching user data:', error);
			});
	}, [userId]);
	
	return (
		<div className="userProfile">
			{/* Component render logic */}
		</div>
	);
}
```

### Code Structure
- Establish all imports, configurations, and setup at the beginning
- Define functions/components before using them
- Follow established best practices for each language
- Maintain clear separation of concerns

## Communication Style

### Implementation Explanations
- Always explain WHY a particular approach was chosen
- Describe what each command does before running it
- Provide context for design decisions
- Example: "I'm using useState here because we need to track data that changes over time in the component"

### Command Explanations
- Before running any command, explain:
	- What the command does
	- Why it's necessary
	- What to expect as output
- Example: "Running 'npm install express' to add Express.js, a web framework that will handle our HTTP requests"

## Project Structure

### Python Projects
```
project-name/
├── src/
│   ├── main.py           # Entry point
│   ├── modules/          # Feature modules
│   └── utils/            # Helper functions
├── tests/                # Test files
├── requirements.txt      # Dependencies
└── README.md
```

### React Projects
```
project-name/
├── src/
│   ├── components/       # React components
│   ├── pages/           # Page components
│   ├── utils/           # Helper functions
│   ├── App.js           # Main app component
│   └── index.js         # Entry point
├── public/              # Static assets
├── package.json         # Dependencies
└── README.md
```

### Java Projects
```
project-name/
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/
│   │           └── projectname/
│   │               ├── Main.java     # Entry point
│   │               ├── models/       # Data models
│   │               └── services/     # Business logic
│   └── test/            # Test files
├── pom.xml              # Maven configuration (if using Maven)
└── README.md
```

## Special Instructions

### Always Do:
- Write code with extensive comments
- Explain critical design decisions and command usage
- Include debugging capabilities in all code
- Follow the established project structure
- Use descriptive names that make code self-documenting

### Never Do:
- Skip comments or explanations
- Use complex one-liners without explanation
- Assume prior knowledge of libraries or frameworks
- Run commands without explaining their purpose

### Future Considerations
- This document can be updated as new preferences emerge
- Additional language or framework preferences can be added later

## Context Priming Reminder
When starting work on any task, always:
1. Read README.md for project overview
2. Read this CLAUDE.md for coding guidelines
3. Run `git ls-files` to understand project structure
4. Review existing code to match patterns

Last Updated: 2024