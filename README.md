# SColorKit

Colons can be used to align columns.

| Colors        | 
| ------------- |
| <img width="1153" alt="image" src="https://github.com/sang200515/SColorKit/assets/75377272/945d01fa-32bd-4c57-bab2-8e7623daeec4">





```swift

struct ContentView: View {
    @State var textfield: String = "2312"
    let colors: [Color] = [.red, .orange, .yellow, .green, .mint, .teal, .cyan, .blue, .indigo, .purple, .pink, .brown, .white, .gray, .black, .accentColor, .primary, .secondary]

    var body: some View {
        ScrollView(.vertical) {
            VStack (spacing: 4){
                ForEach(colors, id: \.self) { colorItem in
                    HStack {
                        Text(colorItem.description.capitalized) // Displaying the title of the color
                            .bold()
                            .font(.system(size: 30, weight: .bold))
                            .foregroundColor(colorItem)
                        Spacer()
                        ForEach((1...10).reversed(), id: \.self) { item in
                            let opacity = Double(item) / 10.0
                            Rectangle()
                                .frame(width: 80, height: 65)
                                .foregroundColor(colorItem.opacity(opacity))
                                .overlay {
                                    Text("\(String(format: "%.1f", opacity))")
                                        .foregroundColor(.primary)
                                }
                        }
                    }

                }
            }   .padding()
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```
