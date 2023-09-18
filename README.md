# SColorKit

Colons can be used to align columns.

| Colors        | 
| ------------- |
|  <img width="1371" alt="image" src="https://github.com/sang200515/SColorKit/assets/75377272/72dedc2f-b49a-4532-a8a8-93b85a92956b">



```swift

struct ContentView: View {
    @State var textfield: String = "2312"
    let colors: [Color] = [.red, .orange, .yellow, .green, .mint, .teal, .cyan, .blue, .indigo, .purple, .pink, .brown, .white, .gray, .black, .clear, .primary, .secondary]

    var body: some View {
        ScrollView(.vertical) {
            VStack {
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
                                .frame(width: 80, height: 55)
                                .foregroundColor(colorItem.opacity(opacity))
                                .overlay {
                                    Text("\(String(format: "%.1f", opacity))")
                                        .foregroundColor(.primary)
                                        .padding()
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
